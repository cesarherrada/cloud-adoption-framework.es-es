---
title: Cumplimiento operativo en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Garantice la estabilidad empresarial al aumentar el cumplimiento operativo
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 9109a51a85627f3c8d0cee8b72baa0936d56c98e
ms.sourcegitcommit: 7df593a67a2e77b5f61c815814af9f0c36ea5ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "75781817"
---
# <a name="operational-compliance-in-azure"></a>Cumplimiento operativo en Azure

El _cumplimiento operativo_ es la segunda materia en cualquier línea de referencia de administración en la nube.

![Línea de base de administración en la nube](../../_images/manage/management-baseline.png)

La mejora del cumplimiento operativo reduce la probabilidad de una interrupción relacionada con el desfase en la configuración o vulnerabilidades relacionadas con sistemas que se han revisado de forma incorrecta.

Para cualquier entorno de nivel empresarial, en esta tabla se describen los mínimos sugeridos para una línea de referencia de administración.

|Proceso  |Herramienta  |Propósito  |
|---------|---------|---------|
|Administración de revisiones|Administración de actualizaciones|Administración y programación de actualizaciones|
|Aplicación de directivas|Azure Policy|Aplicación de directivas para garantizar el cumplimiento del entorno y el invitado|
|Configuración del entorno|Azure Blueprint|Compatibilidad automatizada para servicios principales|
|Configuración de recurso|Configuración de estado deseado|Configuración automatizada en el sistema operativo invitado y algunos aspectos del entorno|

::: zone target="docs"

## <a name="update-management"></a>Administración de actualizaciones

::: zone-end
::: zone target="chromeless"

## <a name="update-managementtabupdatemanagement"></a>[Administración de actualizaciones](#tab/UpdateManagement)

::: zone-end

Los equipos administrados por Update Management usan las siguientes configuraciones para evaluar e implementar actualizaciones:

- Microsoft Monitoring Agent (MMA) para Windows o Linux
- Extensión DSC (configuración de estado deseado) de PowerShell para Linux
- Hybrid Runbook Worker de Azure Automation
- Microsoft Update o Windows Server Update Services (WSUS) para equipos Windows

Para obtener más información, consulte [Solución Update Management](https://docs.microsoft.com/azure/automation/automation-update-management).

> [!WARNING]
> Antes de usar Update Management, debe incorporar máquinas virtuales o una suscripción completa en Log Analytics y Azure Automation.
>
> Hay dos enfoques en la incorporación:
>
> - [Una única máquina virtual](https://docs.microsoft.com/azure/cloud-adoption-framework/manage/azure-server-management/onboard-single-vm)
> - [Toda la suscripción](https://docs.microsoft.com/azure/cloud-adoption-framework/manage/azure-server-management/onboard-at-scale)
>
> Debe seguir uno para poder continuar con Update Management.

### <a name="manage-updates"></a>Administración de actualizaciones

Para aplicar una directiva a un grupo de recursos:

1. Vaya a [Azure Automation](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Automation%2FAutomationAccounts).
1. Seleccione **Cuentas de Automation** y elija una de las cuentas de la lista.
1. Diríjase a **Administración de configuración**.
1. **Inventario**, **Administración de cambios** y **State Configuration** pueden usarse para controlar el estado y el cumplimiento operativo de las VM administradas.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Automation%2FAutomationAccounts]" submitText="Assign Policy" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

## <a name="azure-policy"></a>Azure Policy

::: zone-end
::: zone target="chromeless"

## <a name="azure-policytabazurepolicy"></a>[Azure Policy](#tab/AzurePolicy)

::: zone-end

Azure Policy se utiliza en los procesos de gobierno. También es muy útil en los procesos de administración en la nube. Azure Policy puede auditar y corregir los recursos de Azure, además de auditar la configuración en una máquina. La validación se realiza mediante el cliente y la extensión Guest Configuration. La extensión, a través del cliente, valida opciones de configuración como:

- Configuración del sistema operativo.
- Configuración o presencia de la aplicación.
- Configuración del entorno.

Actualmente, la configuración de invitado de Azure Policy solo realiza la auditoría de la configuración dentro de la máquina. No aplica configuraciones.

::: zone target="chromeless"

### <a name="action"></a>Acción

Asigne una directiva integrada a un grupo de administración, suscripción o grupo de recursos.

::: form action="OpenBlade[#blade/Microsoft_Azure_Policy/PolicyMenuBlade/GettingStarted]" submitText="Assign Policy" :::

::: zone-end

::: zone target="docs"

### <a name="apply-a-policy"></a>Aplicación de una directiva

Para aplicar una directiva a un grupo de recursos:

1. Vaya a [Azure Policy](https://portal.azure.com/#blade/Microsoft_Azure_Policy/PolicyMenuBlade/GettingStarted).
1. Seleccione **Asignar una directiva**.

### <a name="learn-more"></a>Más información

Para obtener más información, consulte:

- [Azure Policy](https://docs.microsoft.com/azure/azure-policy)
- [Azure Policy: extensión Guest Configuration](https://docs.microsoft.com/azure/governance/policy/concepts/guest-configuration)
- [Plataforma de adopción de la nube: Guía de decisiones sobre el cumplimiento de directivas](../../decision-guides/policy-enforcement/index.md)

## <a name="azure-blueprints"></a>Azure Blueprint

::: zone-end
::: zone target="chromeless"

## <a name="azure-blueprintstabazureblueprints"></a>[Azure Blueprints](#tab/AzureBlueprints)

::: zone-end

Con Azure Blueprints, los arquitectos de la nube y los grupos de TI central pueden definir un conjunto repetible de recursos de Azure. Estos recursos implementan y cumplen los estándares, patrones y requisitos de una organización.

Con Azure Blueprints, los equipos de desarrollo pueden crear y erigir rápidamente nuevos entornos. Los equipos también pueden tener la certeza de que actúan en conformidad con la organización. Para ello, usan un conjunto de componentes integrados como redes para acelerar el desarrollo y la entrega.

Los planos técnicos son una manera declarativa de organizar la implementación de distintas plantillas de recursos y de otros artefactos, como son:

- Asignaciones de roles.
- Asignaciones de directivas.
- Plantillas de Azure Resource Manager.
- Grupos de recursos.

La aplicación de un plano técnico puede exigir el cumplimiento operativo en un entorno, si aún no lo exige el equipo de gobernanza de la nube.

### <a name="create-a-blueprint"></a>Creación de un plano técnico

Para crear un plano técnico, realice el siguiente procedimiento:

::: zone target="chromeless"

1. Vaya a **Introducción a planos técnicos**.
1. En el panel **Crear un plano técnico**, seleccione **Crear**.
1. Filtre la lista Planos técnicos para seleccionar el plano técnico adecuado.
1. En el cuadro **Nombre del plano técnico**, escriba el nombre del plano técnico.
1. Seleccione **Ubicación de definición** y elija la ubicación correspondiente.
1. Seleccione **Siguiente: Artefactos >>** y revise los artefactos incluidos en el plano técnico.
1. Seleccione **Guardar borrador**.

::: form action="OpenBlade[#blade/Microsoft_Azure_Policy/BlueprintsMenuBlade/GetStarted]" submitText="Create a blueprint" :::

::: zone-end

::: zone target="docs"

1. Vaya a [Introducción a planos técnicos](https://portal.azure.com/#blade/Microsoft_Azure_Policy/BlueprintsMenuBlade/GetStarted).
1. En el panel **Crear un plano técnico**, seleccione **Crear**.
1. Filtre la lista Planos técnicos para seleccionar el plano técnico adecuado.
1. En el cuadro **Nombre del plano técnico**, escriba el nombre del plano técnico.
1. Seleccione **Ubicación de definición** y elija la ubicación correspondiente.
1. Seleccione **Siguiente: Artefactos >>** y revise los artefactos incluidos en el plano técnico.
1. Seleccione **Guardar borrador**.

::: zone-end

### <a name="publish-a-blueprint"></a>Publicación de un plano técnico

Para publicar artefactos de plano técnico en su suscripción, haga lo siguiente:

::: zone target="chromeless"

1. Vaya a **Planos técnicos - Definiciones del plano técnico**.
1. Seleccione el plano técnico que creó en los pasos anteriores.
1. Revise la definición del plano técnico y seleccione **Publicar plano técnico**.
1. En el cuadro **Versión**, escriba una versión, como "1.0".
1. En el cuadro **Notas de cambios**, introduzca sus notas.
1. Seleccione **Publicar**.

::: form action="OpenBlade[#blade/Microsoft_Azure_Policy/BlueprintsMenuBlade/Blueprints]" submitText="Blueprint definitions" :::

::: zone-end

::: zone target="docs"

1. Vaya a [Planos técnicos - Definiciones del plano técnico](https://portal.azure.com/#blade/Microsoft_Azure_Policy/BlueprintsMenuBlade/Blueprints).
1. Seleccione el plano técnico que creó en los pasos anteriores.
1. Revise la definición del plano técnico y seleccione **Publicar plano técnico**.
1. En el cuadro **Versión**, escriba una versión, como "1.0".
1. En el cuadro **Notas de cambios**, introduzca sus notas.
1. Seleccione **Publicar**.

<!-- markdownlint-disable MD024 -->

### <a name="learn-more"></a>Más información

Para obtener más información, consulte:

- [Azure Blueprints](https://docs.microsoft.com/azure/governance/blueprints)
- [Plataforma de adopción de la nube: Guía de decisiones de la coherencia de recursos](../../decision-guides/resource-consistency/index.md)
- [Ejemplos de planos técnicos basados en estándares](https://docs.microsoft.com/azure/governance/blueprints/samples/index#standards-based-blueprint-samples)

::: zone-end
