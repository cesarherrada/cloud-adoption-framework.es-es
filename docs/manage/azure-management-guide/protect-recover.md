---
title: Protección y recuperación en Azure
description: Garantiza la estabilidad empresarial al reducir el tiempo de recuperación
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 3e9eadbd246ba38f496d8c74b7bcd3e6ade03685
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76808165"
---
# <a name="protect-and-recover-in-azure"></a>Protección y recuperación en Azure

La materia de _protección y recuperación_ es la tercera y última en cualquier base de referencia para la administración en la nube.

![Línea de base de administración en la nube](../../_images/manage/management-baseline.png)

En [Cumplimiento operativo en Azure](./operational-compliance.md), el objetivo es reducir la probabilidad de una interrupción del negocio. El artículo actual tiene el objetivo de reducir la duración y el impacto de las interrupciones que no se pueden evitar.

Para cualquier entorno de nivel empresarial, en esta tabla se describen los mínimos sugeridos para cualquier base de referencia de administración:

|Proceso  |Herramienta  |Propósito  |
|---------|---------|---------|
|Protección de datos|Azure Backup|Realizar copias de seguridad de los datos y las máquinas virtuales en la nube.|
|Protección del entorno|Azure Security Center|Reforzar la seguridad y proporcionar protección contra amenazas avanzada en todas las cargas de trabajo híbridas.|

::: zone target="docs"

## <a name="azure-backup"></a>Azure Backup

::: zone-end
::: zone target="chromeless"

## <a name="azure-backuptabupdbackupatemanagement"></a>[Azure Backup](#tab/UpdbackupateManagement)

::: zone-end

Con Azure Backup puede crear copias de seguridad de sus datos, así como protegerlos y recuperarlos, en la nube de Microsoft. Azure Backup reemplaza su solución de copia de seguridad local o remota existente por una solución basada en la nube. Esta nueva solución es confiable, segura y rentable. Azure Backup también puede ayudar a proteger y recuperar los recursos locales a través de una solución coherente.

### <a name="enable-backup-for-an-azure-vm"></a>Habilitación de la copia de seguridad de una máquina virtual de Azure

1. En Azure Portal, seleccione **Máquinas virtuales** y la máquina virtual que desea replicar.
1. En el panel **Operaciones**, seleccione **Copia de seguridad**.
1. Cree un almacén de Azure Recovery Services o seleccione uno existente.
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

Site Recovery replica las VM y las cargas de trabajo que se hospedan en una región principal de Azure. Las replica en una copia que se hospeda en una región secundaria. Cuando se produce una interrupción en la región primaria, se realiza una conmutación por error en la copia que se ejecuta en la región secundaria. Después puede seguir accediendo a sus aplicaciones y servicios desde allí. Este enfoque proactivo hacia la recuperación puede reducir significativamente los tiempos de recuperación. Cuando el entorno de recuperación ya no es necesario, el tráfico de producción puede revertirse al entorno original.

### <a name="replicate-an-azure-vm-to-another-region-with-site-recovery"></a>Replicación de una VM de Azure en otra región con Site Recovery

En los pasos siguientes se describe el proceso para usar Site Recovery servicio para la replicación de Azure a Azure, que consiste en replicar una VM de Azure en otra región:
>
> [!TIP]
> Los pasos exactos pueden diferir ligeramente según el escenario.
>

### <a name="enable-replication-for-the-azure-vm"></a>Habilitación de la replicación para la máquina virtual de Azure

1. En Azure Portal, seleccione **Máquinas virtuales** y la máquina virtual que desea replicar.
1. En el panel **Operaciones**, seleccione **Recuperación ante desastres**.
1. Seleccione **Configurar la recuperación ante desastres** > **Región de destino** y elija la región de destino en la que quiere realizar la replicación.
1. Para esta guía de inicio rápido, acepte los valores predeterminados de todas las demás opciones.
1. Seleccione **Habilitar replicación** para habilitar la replicación de la máquina virtual.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/Resources/resourceType/Microsoft.Compute%2FVirtualMachines]" submitText="Go to Virtual Machines" :::

::: zone-end

### <a name="verify-settings"></a>Comprobación de la configuración

Cuando haya finalizado el trabajo de replicación, puede comprobar el estado de la replicación y probar la implementación.

1. En el menú de la máquina virtual, seleccione **Recuperación ante desastres**.
1. Compruebe el estado de la replicación, los puntos de recuperación que se crearon y las regiones de origen y destino en el mapa.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/Resources/resourceType/Microsoft.Compute%2FVirtualMachines]" submitText="Go to Virtual Machines" :::

::: zone-end

### <a name="learn-more"></a>Más información

- [Información general sobre Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)
- [Replicación de una máquina virtual de Azure en otra región](https://docs.microsoft.com/azure/site-recovery/azure-to-azure-quickstart)
