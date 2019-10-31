---
title: Aceleración de la migración con hosts de VMWare
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aceleración de la migración con hosts de VMWare
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: b09c1dcbb36e5f630ca0ae86c95c5c874e29d60b
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72558610"
---
# <a name="accelerate-migration-with-vmware-hosts"></a>Aceleración de la migración con hosts de VMWare

La migración de hosts de VMWare completos puede conllevar el traslado de varias cargas de trabajo y recursos en un solo trabajo de migración. La siguiente guía ampliará el ámbito de la [guía de migración de Azure](../azure-migration-guide/index.md) con la migración de hosts de VMWare.

## <a name="general-scope-expansion"></a>Ampliación del ámbito general

La mayor parte del trabajo que se requiere en esta expansión del ámbito se producirá durante los procesos de requisitos previos y migración.

## <a name="suggested-prerequisites"></a>Requisitos previos sugeridos

Al migrar el primer host de VMWare a Azure, hay una serie de requisitos previos que deben cumplirse para preparar los requisitos de identidad, red y administración. Si se cumplen estos requisitos previos, cada host adicional requerirá un trabajo significativamente menor para la migración. Estos requisitos previos se alinean con algunos trabajos clave: protección del entorno de Azure, administración de la nube privada y redes de la nube privada.

### <a name="secure-your-azure-environment"></a>Protección del entorno de Azure

Implemente la solución adecuada en la nube para el control de acceso basado en rol y la conectividad de red del entorno de Azure. La guía [Protección del entorno](https://docs.microsoft.com/azure/vmware-cloudsimple/private-cloud-secure.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json) puede ayudarle con esta implementación.

### <a name="private-cloud-management"></a>Administración de la nube privada

Hay dos tareas obligatorias y una tarea opcional para establecer la administración de la nube privada. [Escalado de privilegios de nube privada](https://docs.microsoft.com/azure/vmware-cloudsimple/escalate-privileges.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json) y [Configuración de DNS y DHCP de carga de trabajo](https://docs.microsoft.com/azure/vmware-cloudsimple/dns-dhcp-setup.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json) son los procedimientos recomendados obligatorios.

Si el objetivo es [migrar cargas de trabajo mediante redes extendidas de nivel 2](https://docs.microsoft.com/azure/vmware-cloudsimple/migration-layer-2-vpn.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json), también se necesitará este tercer procedimiento recomendado.

### <a name="private-cloud-networking"></a>Redes de la nube privada

Una vez establecidos los requisitos de administración, se pueden establecer las redes de la nube privada mediante los siguientes procedimientos recomendados:

- [Conexión VPN a la nube privada](https://docs.microsoft.com/azure/vmware-cloudsimple/set-up-vpn.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Conexión de red local con ExpressRoute](https://docs.microsoft.com/azure/vmware-cloudsimple/on-premises-connection.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Conexión de red virtual de Azure con ExpressRoute](https://docs.microsoft.com/azure/vmware-cloudsimple/azure-expressroute-connection.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Configuración de la resolución de nombres de DNS](https://docs.microsoft.com/azure/vmware-cloudsimple/on-premises-dns-setup.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

### <a name="integration-with-the-cloud-adoption-plan"></a>Integración con el plan de adopción de la nube

Una vez que se cumplen los requisitos previos, cada host de VMWare se incluye en el [plan de adopción de la nube](../../plan/template.md). En el plan de adopción de la nube, agregue cada host que se va a migrar como una [carga de trabajo distinta](../../plan/workloads.md). En cada carga de trabajo, las máquinas virtuales que se van a migrar se pueden agregar como [recursos](../../plan/workloads.md). Para agregar cargas de trabajo y recursos de forma masiva al plan de adopción, consulte [Agregar y editar elementos de trabajo con Excel](https://docs.microsoft.com/azure/devops/boards/backlogs/office/bulk-add-modify-work-items-excel?view=azure-devops).

## <a name="migrate-process-changes"></a>Cambios en el proceso de migración

Durante cada iteración, el equipo de adopción analiza el trabajo pendiente para migrar las cargas de trabajo de prioridad más alta. El proceso no cambia realmente en el caso de los hosts de VMWare. Si la siguiente carga de trabajo del trabajo pendiente es un host de VMWare, el único cambio consiste en la herramienta que se emplea.

### <a name="suggested-action-during-the-migrate-process"></a>Acción sugerida durante el proceso de migración

A continuación, se muestran algunos ejemplos de las herramientas que se pueden utilizar en un proceso de migración:

- [VMWare Tools nativo](https://docs.microsoft.com/azure/vmware-cloudsimple/migrate-workloads.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Azure Data Box](https://docs.microsoft.com/azure/vmware-cloudsimple/migration-using-azure-data-box.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

Como alternativa, las cargas de trabajo se pueden migrar mediante una conmutación por error de recuperación ante desastres con las siguientes herramientas:

- [Copia de seguridad de máquinas virtuales de carga de trabajo](https://docs.microsoft.com/azure/vmware-cloudsimple/backup-workloads-veeam.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Configuración de la nube privada como sitio de recuperación ante desastres mediante Zerto](https://docs.microsoft.com/azure/vmware-cloudsimple/disaster-recovery-zerto.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Configuración de la nube privada como sitio de recuperación ante desastres mediante VMware SRM](https://docs.microsoft.com/azure/vmware-cloudsimple/disaster-recovery-site-recovery-manager.md?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

## <a name="next-steps"></a>Pasos siguientes

Vuelva a la [lista de comprobación del ámbito ampliado](./index.md) para asegurarse de que el método de migración está totalmente alineado.

> [!div class="nextstepaction"]
> [Lista de comprobación del ámbito ampliado](./index.md)
