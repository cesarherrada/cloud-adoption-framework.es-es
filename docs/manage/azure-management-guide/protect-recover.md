---
title: Protección y recuperación en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Garantice la estabilidad empresarial al reducir el tiempo de recuperación
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: a79164435772f571849d0a836f43b53ce3bca087
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72557013"
---
# <a name="protect-and-recover-in-azure"></a>Protección y recuperación en Azure

La protección y recuperación es la tercera y última disciplina en cualquier línea de base para la administración en la nube.

![Línea de base de administración en la nube](../../_images/manage/management-baseline.png)

En el último artículo, "Cumplimiento operativo", el objetivo era reducir la probabilidad de una interrupción del negocio. En este artículo, "Protección y recuperación", se pretende reducir la duración y el impacto de las interrupciones que no se pueden evitar.

En el caso de cualquier entorno de nivel empresarial, en la tabla siguiente se describen los mínimos sugeridos para cualquier línea de base de administración.

|Proceso  |Herramienta  |Propósito  |
|---------|---------|---------|
|Protección de datos|Azure Backup|Copia de seguridad de datos y máquinas virtuales en la nube|
|Protección del entorno|Azure Security Center|

::: zone target="docs"

## <a name="azure-backup"></a>Azure Backup

::: zone-end
::: zone target="chromeless"

## <a name="azure-backuptabupdbackupatemanagement"></a>[Azure Backup](#tab/UpdbackupateManagement)

::: zone-end

Azure Backup es el servicio de Azure que puede usar para hacer una copia de seguridad de los datos (o protegerlos) y recuperarlos en Microsoft Cloud. Azure Backup reemplaza su solución de copia de seguridad local o remota existente por una solución confiable, segura y rentable basada en la nube. También se puede usar para proteger y recuperar los recursos locales a través de una solución coherente.

### <a name="enable-backup-for-an-azure-vm"></a>Habilitación de la copia de seguridad de una máquina virtual de Azure

1. En Azure Portal, seleccione **Máquinas virtuales** y la máquina virtual que desea replicar.
1. En **Operaciones**, seleccione **Copia de seguridad**.
1. Cree un almacén de Recovery Services o seleccione uno existente.
1. Seleccione **Crear una nueva directiva (o editar una)** .
1. Configure la programación y el período de retención.
1. Seleccione **Aceptar**.
1. Seleccione **Habilitar copia de seguridad**.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/Resources/resourceType/Microsoft.Compute%2FVirtualMachines]" submitText="Go to Virtual Machines" :::

::: zone-end

::: zone target="docs"

[Información general](https://docs.microsoft.com/azure/backup/backup-introduction-to-azure-backup)

## <a name="azure-site-recovery"></a>Azure Site Recovery

::: zone-end
::: zone target="chromeless"

## <a name="azure-site-recoverytabsiterecovery"></a>[Azure Site Recovery](#tab/siterecovery)

::: zone-end

Azure Site Recovery es un componente esencial de la estrategia de recuperación ante desastres.

El servicio Azure Site Recovery le permite replicar máquinas virtuales y cargas de trabajo hospedadas en una región primaria de Azure en una copia hospedada en una región secundaria. Cuando se produce una interrupción en la región primaria, puede conmutar por error en la copia que se ejecuta en la región secundaria y seguir accediendo a sus aplicaciones y servicios desde allí. Este enfoque proactivo hacia la recuperación puede reducir significativamente los tiempos de recuperación. Cuando el entorno de recuperación ya no es necesario, el tráfico de producción puede revertirse al entorno original.

### <a name="replicate-an-azure-vm-to-another-region-with-site-recovery-service"></a>Replicación de una máquina virtual de Azure en otra región con el servicio Site Recovery

En los pasos siguientes se describe el proceso para usar Site Recovery servicio para replicar una máquina virtual de Azure en otra región (de Azure a Azure):

>
> [!TIP]
> Los pasos exactos pueden diferir ligeramente según el escenario.
>

### <a name="enable-replication-for-the-azure-vm"></a>Habilitación de la replicación para la máquina virtual de Azure

1. En Azure Portal, seleccione **Máquinas virtuales** y la máquina virtual que desea replicar.
1. En **Operaciones**, seleccione **Recuperación ante desastres**.
1. En **Configurar la recuperación ante desastres** > **Región de destino**, seleccione la región de destino en la que quiere realizar la replicación.
1. En esta guía de inicio rápido, acepte los restantes valores predeterminados.
1. Seleccione **Habilitar replicación** para habilitar la replicación de la máquina virtual.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/Resources/resourceType/Microsoft.Compute%2FVirtualMachines]" submitText="Go to Virtual Machines" :::

::: zone-end

### <a name="verify-settings"></a>Comprobación de la configuración

Cuando haya finalizado el trabajo de replicación, puede comprobar el estado de la replicación y probar la implementación.

1. En el menú de la máquina virtual, seleccione **Recuperación ante desastres**.
2. Compruebe el estado de la replicación, los puntos de recuperación que se crearon y las regiones de origen y destino en el mapa.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/Resources/resourceType/Microsoft.Compute%2FVirtualMachines]" submitText="Go to Virtual Machines" :::

::: zone-end

### <a name="learn-more"></a>Más información

- [Información general sobre Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)
- [Replicación de una máquina virtual de Azure en otra región](https://docs.microsoft.com/azure/site-recovery/azure-to-azure-quickstart)
