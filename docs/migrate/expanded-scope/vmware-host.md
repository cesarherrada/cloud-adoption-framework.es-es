---
title: Aceleración de la migración con hosts de VMware
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aceleración de la migración con hosts de VMware
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 724a227407f431e08b5344dfd1280397bfca9b65
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73566884"
---
# <a name="accelerate-migration-with-vmware-hosts"></a>Aceleración de la migración con hosts de VMware

La migración de hosts de VMware completos puede conllevar el traslado de varias cargas de trabajo y recursos en un solo trabajo de migración. La siguiente guía amplía el ámbito de la [guía de migración de Azure](../azure-migration-guide/index.md) a través de una migración de hosts de VMware. La mayor parte del trabajo que se requiere en esta expansión del ámbito se produce durante los procesos de requisitos previos y migración.

## <a name="suggested-prerequisites"></a>Requisitos previos sugeridos

Al migrar el primer host de VMware a Azure, debe cumplir varios requisitos previos para preparar los requisitos de identidad, red y administración. Una vez que se cumplan estos requisitos previos, cada host adicional debería requerir un trabajo significativamente menor para la migración. En las siguientes secciones, se proporcionan más detalles sobre los requisitos previos.

### <a name="secure-your-azure-environment"></a>Protección del entorno de Azure

Implemente la solución adecuada en la nube para el control de acceso basado en rol y la conectividad de red en el entorno de Azure. La guía [Protección del entorno](https://docs.microsoft.com/azure/vmware-cloudsimple/private-cloud-secure?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json) puede ayudarle con esta implementación.

### <a name="private-cloud-management"></a>Administración de la nube privada

Hay dos tareas obligatorias y una tarea opcional para establecer la administración de la nube privada. [Escalado de privilegios de nube privada](https://docs.microsoft.com/azure/vmware-cloudsimple/escalate-privileges?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json) y [Configuración de DNS y DHCP de carga de trabajo](https://docs.microsoft.com/azure/vmware-cloudsimple/dns-dhcp-setup?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json) son los procedimientos recomendados obligatorios.

Si el objetivo es [migrar cargas de trabajo mediante redes extendidas de nivel 2](https://docs.microsoft.com/azure/vmware-cloudsimple/migration-layer-2-vpn?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json), también se necesitará este tercer procedimiento recomendado.

### <a name="private-cloud-networking"></a>Redes de la nube privada

Una vez establecidos los requisitos de administración, se pueden establecer las redes de la nube privada mediante los siguientes procedimientos recomendados:

- [Conexión VPN a la nube privada](https://docs.microsoft.com/azure/vmware-cloudsimple/set-up-vpn?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Conexión de red local con ExpressRoute](https://docs.microsoft.com/azure/vmware-cloudsimple/on-premises-connection?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Conexión de red virtual de Azure con ExpressRoute](https://docs.microsoft.com/azure/vmware-cloudsimple/azure-expressroute-connection?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Configuración de la resolución de nombres de DNS](https://docs.microsoft.com/azure/vmware-cloudsimple/on-premises-dns-setup?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

### <a name="integration-with-the-cloud-adoption-plan"></a>Integración con el plan de adopción de la nube

Una vez cumplidos los otros requisitos previos, debería incluir cada host de VMware en el [plan de adopción de la nube](../../plan/template.md). En el plan de adopción de la nube, agregue cada host que se va a migrar como una [carga de trabajo distinta](../../plan/workloads.md). En cada carga de trabajo, agregue las VM que se van a migrar como [recursos](../../plan/workloads.md). Para agregar cargas de trabajo y recursos de forma masiva al plan de adopción, consulte el tema sobre cómo [agregar y editar elementos de trabajo con Excel](https://docs.microsoft.com/azure/devops/boards/backlogs/office/bulk-add-modify-work-items-excel?view=azure-devops).

## <a name="migrate-process-changes"></a>Cambios en el proceso de migración

Durante cada iteración, el equipo de adopción analiza el trabajo pendiente para migrar las cargas de trabajo de prioridad más alta. El proceso no cambia realmente en el caso de los hosts de VMware. Si la siguiente carga de trabajo del trabajo pendiente es un host de VMware, el único cambio consiste en la herramienta que se emplea.

Puede usar las siguientes herramientas en el trabajo de migración:

- [Herramientas de VMware nativas](https://docs.microsoft.com/azure/vmware-cloudsimple/migrate-workloads?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Azure Data Box](https://docs.microsoft.com/azure/vmware-cloudsimple/migration-using-azure-data-box?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

Como alternativa, puede migrar las cargas de trabajo mediante una conmutación por error de recuperación ante desastres con las siguientes herramientas:

- [Copia de seguridad de máquinas virtuales de carga de trabajo](https://docs.microsoft.com/azure/vmware-cloudsimple/backup-workloads-veeam?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Configuración de la nube privada como sitio de recuperación ante desastres mediante Zerto](https://docs.microsoft.com/azure/vmware-cloudsimple/disaster-recovery-zerto?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)
- [Configuración de la nube privada como sitio de recuperación ante desastres mediante VMware SRM](https://docs.microsoft.com/azure/vmware-cloudsimple/disaster-recovery-site-recovery-manager?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

## <a name="next-steps"></a>Pasos siguientes

Vuelva a la lista de comprobación del ámbito ampliado para asegurarse de que el método de migración está totalmente alineado.

> [!div class="nextstepaction"]
> [Lista de comprobación del ámbito ampliado](./index.md)
