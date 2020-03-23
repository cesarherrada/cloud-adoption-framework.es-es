---
title: Configuración del servicio para una suscripción
description: Aprenda a configurar los servicios de administración de servidores de Azure de una suscripción mediante la implementación de agentes de servicio en los servidores y la habilitación de soluciones de administración.
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: efd387f2f3a1c11d518e8e51d06977efdd07609c
ms.sourcegitcommit: 5411c3b64af966b5c56669a182d6425e226fd4f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79312739"
---
<!-- cSpell:ignore VMUUID kusto -->

# <a name="configure-azure-server-management-services-at-scale"></a>Configuración de servicios de administración de servidores de Azure a escala

Debe completar estas dos tareas para incorporar los servicios de administración de servidores de Azure en sus servidores:

- Implementar los agentes de servicio en los servidores
- Habilitar las soluciones de administración

En este artículo se tratan los siguientes tres procesos necesarios para realizar estas tareas:

1. Implementar los agentes necesarios en las VM de Azure mediante Azure Policy
1. Implementar los agentes necesarios en servidores locales
1. Habilitar y configurar las soluciones

> [!NOTE]
> Cree el [área de trabajo de Log Analytics y la cuenta de Azure Automation](./prerequisites.md#create-a-workspace-and-automation-account) necesarias antes de incorporar máquinas virtuales a los servicios de administración de servidores de Azure.

## <a name="use-azure-policy-to-deploy-extensions-to-azure-vms"></a>Uso de Azure Policy para implementar extensiones en VM de Azure

Todas las soluciones de administración descritas en el artículo sobre [servicios y herramientas de administración de Azure](./tools-services.md) requieren que el agente de Log Analytics esté instalado en las máquinas virtuales de Azure y en los servidores locales. Puede incorporar sus máquinas virtuales de Azure a escala mediante Azure Policy. Asigne una directiva para asegurarse de que el agente esté instalado en sus VM de Azure y conectado al área de trabajo de Log Analytics correcta.

Azure Policy tiene una [iniciativa de directiva](https://docs.microsoft.com/azure/governance/policy/concepts/definition-structure#initiatives) integrada que incluye el agente de Log Analytics y [Microsoft Dependency Agent](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-onboard#the-microsoft-dependency-agent), que Azure Monitor para VM requiere.

<!-- TODO: Add these when available.
- [Preview]: Enable Azure Monitor for virtual machine scale sets.
- [Preview]: Enable Azure Monitor for VMs.
 -->

> [!NOTE]
> Para obtener más información sobre distintos agentes de supervisión de Azure, consulte [Introducción a los agentes de supervisión de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agents-overview).

### <a name="assign-policies"></a>Asignación de directivas

Para asignar las directivas que se describen en la sección anterior:

1. En Azure Portal, vaya a **Azure Policy** > **Asignaciones** > **Asignar iniciativa**.

    ![Captura de pantalla de la interfaz de directivas del portal](./media/onboarding-at-scale1.png)

2. En la página **Asignar directiva**, seleccione los puntos suspensivos (…) para establecer la opción de **Ámbito** y seleccione una suscripción o un grupo de administración. Opcionalmente, seleccione un grupo de recursos. Luego elija **Seleccionar** en la parte inferior de la página **Ámbito**. El ámbito determina los recursos o el grupo de recursos a los que se asigna la directiva.

3. Seleccione los puntos suspensivos ( **…** ) que aparecen junto a **Definición de directiva** para abrir la lista de definiciones disponibles. Para filtrar las definiciones de iniciativa, escriba **Azure Monitor** en el cuadro de **búsqueda**:

    ![Captura de pantalla de la interfaz de directivas del portal](./media/onboarding-at-scale2.png)

4. **Nombre de asignación** se rellena automáticamente con el nombre de directiva seleccionado, pero puede cambiarlo. También puede agregar una descripción opcional para proporcionar más información sobre esta asignación de directiva. El campo **Asignado por** se rellena automáticamente en función de quién inicie sesión. Este campo es opcional y admite valores personalizados.

5. Para esta directiva, seleccione **Área de trabajo de Log Analytics** como agente de Log Analytics que se va a asociar.

    ![Captura de pantalla de la interfaz de directivas del portal](./media/onboarding-at-scale3.png)

6. Seleccione la casilla **Ubicación de la identidad administrada**. Si esta directiva es de tipo [DeployIfNotExists](https://docs.microsoft.com/azure/governance/policy/concepts/effects#deployifnotexists), se necesitará una identidad administrada para implementar la directiva. En el portal, la cuenta se creará como se indica con la selección de la casilla.

7. Seleccione **Asignar**.

Después de completar el asistente, la asignación de directiva se implementará en el entorno. La directiva puede tardar hasta 30 minutos en surtir efecto. Para probarla, cree VM después de 30 minutos y compruebe si Microsoft Monitoring Agent se habilita en la VM de forma predeterminada.

## <a name="install-agents-on-on-premises-servers"></a>Instalación de los agentes en servidores locales

> [!NOTE]
> Cree el [área de trabajo de Log Analytics y la cuenta de Azure Automation](./prerequisites.md#create-a-workspace-and-automation-account) necesarias antes de incorporar los servicios de administración de servidores de Azure en los servidores.

En el caso de los servidores locales, debe descargar e instalar manualmente el [agente de Log Analytics y Microsoft Dependency Agent](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-enable-hybrid-cloud), y configurarlos para que se conecten al área de trabajo correcta. Debe especificar el identificador del área de trabajo y la información de clave. Para obtener esa información, vaya al área de trabajo de Log Analytics en Azure Portal y, a continuación, seleccione **Configuración** > **Configuración avanzada**.

![Captura de pantalla de Configuración avanzada del área de trabajo de Log Analytics en Azure Portal](./media/onboarding-on-premises.png)

## <a name="enable-and-configure-solutions"></a>Habilitación y configuración de soluciones

Para habilitar las soluciones, tiene que configurar el área de trabajo Log Analytics. Las VM de Azure y los servidores locales incorporados obtendrán las soluciones de las áreas de trabajo de Log Analytics a las que se han conectado.

### <a name="update-management"></a>Administración de actualizaciones

Las soluciones Update Management, Change Tracking e Inventario requieren un área de trabajo de Log Analytics y una cuenta de Automation. Para asegurarse de que estos recursos están configurados correctamente, se recomienda realizar la incorporación a través de la cuenta de Automation. Para obtener más información, consulte [Incorporación de las soluciones Update Management, Change Tracking e Inventario](https://docs.microsoft.com/azure/automation/automation-onboard-solutions-from-automation-account).

Se recomienda habilitar la solución Update Management para todos los servidores. Update Management es gratis para las máquinas virtuales de Azure y los servidores locales. Si habilita Update Management a través de su cuenta de Automation, se creará una [configuración de ámbito](https://docs.microsoft.com/azure/automation/automation-onboard-solutions-from-automation-account#scope-configuration) en el área de trabajo. Actualice manualmente el ámbito para incluir las máquinas que cubre el servicio Update Management.

Para cubrir los servidores existentes, así como los futuros, debe quitar la configuración de ámbito. Para hacerlo, consulte la cuenta de Automation en Azure Portal. Seleccione **Update Management** > **Administrar máquinas** > **Habilitar en todas las máquinas disponibles y futuras**. Es opción permite que todas las VM de Azure conectadas al área de trabajo usen Update Management.

![Captura de pantalla de Update Management en Azure Portal](./media/onboarding-configuration1.png)

### <a name="change-tracking-and-inventory-solutions"></a>Soluciones Change Tracking e Inventory

Para incorporar soluciones de Change Tracking e Inventory, siga los mismos pasos que para Update Management. Para obtener más información sobre cómo incorporar estas soluciones desde su cuenta de Automation, consulte [Incorporación de las soluciones Update Management, Change Tracking e Inventory](https://docs.microsoft.com/azure/automation/automation-onboard-solutions-from-automation-account).

La solución Change Tracking es gratuita para las máquinas virtuales de Azure y cuesta 6 USD por nodo al mes para los servidores locales. Este costo cubre Change Tracking e Inventory y Desired State Configuration. Si solo quiere inscribir determinados servidores locales, puede participar en esos servidores. Se recomienda que incorpore todos los servidores de producción.

#### <a name="opt-in-via-the-azure-portal"></a>Participación a través de Azure Portal

1. Vaya a la cuenta de Automation que tiene Change Tracking e Inventory habilitada.
2. Seleccione **Seguimiento de cambios**.
3. Seleccione **Administrar máquinas** en el panel superior derecho.
4. Seleccione **Habilitar en las máquinas seleccionadas**. A continuación, seleccione **Agregar** junto al nombre de la máquina.
5. Seleccione **Habilitar** para habilitar la solución para esas máquinas.

![Captura de pantalla de Change Tracking en Azure Portal](./media/onboarding-configuration2.png)

#### <a name="opt-in-by-using-saved-searches"></a>Participación mediante búsquedas guardadas

También puede establecer la configuración de ámbito para participar en servidores locales. La configuración de ámbito usa búsquedas guardadas.

Para crear o modificar la búsqueda guardada, siga estos pasos:

1. Vaya al área de trabajo de Log Analytics que está vinculada a la cuenta de Automation que configuró en los pasos anteriores.

1. En **General**, seleccione **Búsquedas guardadas**.

1. En el cuadro **Filtro**, escriba **Change Tracking** para filtrar la lista de búsquedas guardadas. En los resultados, seleccione **MicrosoftDefaultComputerGroup**.

1. Escriba el VMUUID o el nombre del equipo para incluir los equipos en los que quiere participar con Change Tracking.

    ```kusto
    Heartbeat
    | where AzureEnvironment=~"Azure" or Computer in~ ("list of the on-premises server names", "server1")
    | distinct Computer
    ```

    > [!NOTE]
    > El nombre del servidor debe coincidir exactamente con el valor de la expresión y no debe contener ningún sufijo de nombre de dominio.

1. Seleccione **Guardar**. De forma predeterminada, la configuración de ámbito está vinculada a la búsqueda guardada de **MicrosoftDefaultComputerGroup**. Se actualizará automáticamente.

### <a name="azure-activity-log"></a>Azure Activity Log

[Registro de actividad de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/activity-logs-overview) es una de las secciones de Azure Monitor. Proporciona información sobre los eventos de nivel de suscripción que se producen en Azure.

Para implementar esta solución:

1. En Azure Portal, abra **Todos los servicios** y, a continuación, seleccione **Administración y gobernanza** > **Soluciones**.
2. En la vista **Soluciones**, seleccione **Agregar**.
3. Busque **Activity Log Analytics** y selecciónela.
4. Seleccione **Crear**.

Debe especificar el **nombre del área de trabajo** que creó en la sección anterior donde está habilitada la solución.

### <a name="azure-log-analytics-agent-health"></a>Agent Health para Azure Log Analytics

La solución Agent Health para Azure Log Analytics ofrece información sobre el mantenimiento, el rendimiento y la disponibilidad de los servidores Windows y Linux.

Para implementar esta solución:

1. En Azure Portal, abra **Todos los servicios** y, a continuación, seleccione **Administración y gobernanza** > **Soluciones**.
2. En la vista **Soluciones**, seleccione **Agregar**.
3. Busque **Agent Health para Azure Log Analytics** y selecciónela.
4. Seleccione **Crear**.

Debe especificar el **nombre del área de trabajo** que creó en la sección anterior donde está habilitada la solución.

Una vez completada la creación, la instancia de recurso del área de trabajo muestra **AgentHealthAssessment** al seleccionar **Vista** > **Soluciones**.

### <a name="antimalware-assessment"></a>Evaluación antimalware

La solución Antimalware Assessment le ayuda a identificar los servidores que están infectados o que presentan mayor riesgo de infección por malware.

Para implementar esta solución:

1. En Azure Portal, abra **Todos los servicios** y, a continuación, seleccione **Administración y gobernanza** > **Soluciones**.
2. En la vista **Soluciones**, seleccione **Agregar**.
3. Busque la opción **Antimalware Assessment** y selecciónela.
4. Seleccione **Crear**.

Debe especificar el **nombre del área de trabajo** que creó en la sección anterior donde está habilitada la solución.

Una vez completada la creación, la instancia de recurso del área de trabajo muestra **AntiMalware** al seleccionar **Vista** > **Soluciones**.

### <a name="azure-monitor-for-vms"></a>Azure Monitor para máquinas virtuales

Puede habilitar [Azure Monitor para VM](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-overview) a través de la página de vista de la instancia de VM, tal y como se describe en [Habilitar los servicios de administración en una única máquina virtual para su evaluación](./onboard-single-vm.md). No debe habilitar soluciones directamente desde la página **Soluciones** como hizo con las otras soluciones que se describen en este artículo. Para implementaciones a gran escala, puede ser más fácil usar [automatización](./onboarding-automation.md) para habilitar las soluciones correctas en el área de trabajo.

### <a name="azure-security-center"></a>Azure Security Center

Se recomienda que incorpore todos los servidores como mínimo en el nivel *Gratis* de Azure Security Center. Esta opción le ofrece un nivel básico de evaluaciones de seguridad y recomendaciones de seguridad prácticas para su entorno. La actualización al nivel *Estándar* ofrece ventajas adicionales, que se describen con detalle en la [página de precios de Security Center](https://docs.microsoft.com/azure/security-center/security-center-pricing).

Para habilitar el nivel Gratis de Azure Security Center, siga estos pasos:

1. Vaya a la página **Security Center** del portal.
2. En **POLICY & COMPLIANCE** (DIRECTIVA Y CUMPLIMIENTO), seleccione **Directiva de seguridad**.
3. Busque el recurso del área de trabajo de Log Analytics que ha creado en el panel de la derecha.
4. Seleccione **Editar configuración** para esa área de trabajo.
5. Seleccione **Plan de tarifa**.
6. Seleccione la opción **Gratis**.
7. Seleccione **Guardar**.

## <a name="next-steps"></a>Pasos siguientes

Aprenda a usar la automatización para incorporar servidores y crear alertas.

> [!div class="nextstepaction"]
> [Automatización de la incorporación y configuración de alertas](./onboarding-automation.md)
