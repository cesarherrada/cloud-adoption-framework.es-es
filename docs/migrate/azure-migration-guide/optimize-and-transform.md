---
title: Optimización y promoción
description: Aprenda a revisar la solución para ver posibles áreas de optimización, incluido el diseño de la solución, el ajuste del tamaño de los servicios y el análisis de los costos.
author: matticusau
ms.author: mlavery
ms.date: 02/25/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.custom: fasttrack-new, AQC
ms.localizationpriority: high
ms.openlocfilehash: eff32a369c55011cea8fb8ace2e7bfae28680eda
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80353871"
---
<!-- markdownlint-disable MD025 DOCSMD001 -->

# <a name="test-optimize-and-promote"></a>Prueba, optimización y promoción

Ahora que migró los servicios a Azure, la fase siguiente incluye revisar la solución para ver posibles áreas de optimización. Este esfuerzo podría incluir la revisión del diseño de la solución, el ajuste correcto del tamaño de los servicios y el análisis de los costos.

Esta fase también es una oportunidad para optimizar el entorno y realizar las transformaciones posibles del entorno. Por ejemplo, es posible que haya realizado una migración de "rehospedaje" y ahora que los servicios se ejecutan en Azure, puede revisar la configuración de soluciones o los servicios consumidos y, posiblemente, realizar alguna "refactorización" para modernizar y aumentar la funcionalidad de la solución.

El resto de este artículo se centra en las herramientas para optimizar la carga de trabajo migrada. Cuando se alcanza el equilibrio de rendimiento y costo, ya se puede promocionar a producción una carga de trabajo. Para más información sobre las opciones de promoción, consulte los artículos sobre la mejora de procesos de [Optimización y promoción](../migration-considerations/optimize/index.md).

# <a name="right-size-assets"></a>[Recursos del tamaño correcto](#tab/optimize)

Se puede cambiar el tamaño de todos los servicios de Azure que proporcionan un modelo de costos basado en el consumo mediante Azure Portal, la CLI o PowerShell. El primer paso para ajustar correctamente el tamaño de un servicio es revisar sus métricas de uso. El servicio Azure Monitor proporciona acceso a estas métricas. Puede que tenga que configurar la recopilación de las métricas para el servicio que está analizando y permitir un tiempo adecuado para recopilar datos significativos en función de los patrones de carga de trabajo.

1. Vaya a **Supervisar**.
1. Seleccione **Métricas** y configure el gráfico para que se muestren las métricas del servicio que se va a analizar.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/Microsoft_Azure_Monitoring/AzureMonitoringBrowseBlade/metrics]" submitText="Go to Monitor" :::

::: zone-end

A continuación, se muestran algunos servicios comunes cuyo tamaño se puede cambiar.

## <a name="resize-a-virtual-machine"></a>Cambio de tamaño de una máquina virtual

Azure Migrate realiza un análisis del ajuste de tamaño como parte de la fase de evaluación previa a la migración y las máquinas virtuales migradas con esta herramienta probablemente ya tengan el tamaño correcto en función de los requisitos previos a la migración.

Sin embargo, en el caso de las máquinas virtuales creadas o migradas mediante otros métodos, o en los casos en los que es necesario ajustar los requisitos de las máquinas virtuales posteriores a la migración, es posible que quiera refinar aún más el tamaño de la máquina virtual.

1. Vaya a **Máquinas virtuales**.
1. Seleccione la máquina virtual deseada en la lista.
1. Seleccione **Tamaño** y el nuevo tamaño deseado en la lista. Es posible que tenga que ajustar los filtros para encontrar el tamaño que necesita.
1. Seleccione **Cambiar tamaño**.

El cambio de tamaño de las máquinas virtuales de producción puede generar interrupciones en el servicio. Intente aplicar el ajuste de tamaño correcto en las máquinas virtuales antes de promocionarlas a producción.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Compute%2FVirtualMachines]" submitText="Go to Virtual Machines" :::

::: zone-end

::: zone target="docs"

- [Administración de reservas para los recursos de Azure](https://docs.microsoft.com/azure/billing/billing-manage-reserved-vm-instance)
- [Cambio de tamaño de una máquina virtual Windows](https://docs.microsoft.com/azure/virtual-machines/windows/resize-vm)
- [Cambiar el tamaño de una máquina virtual Linux que usa la CLI de Azure](https://docs.microsoft.com/azure/virtual-machines/linux/change-vm-size)

Los asociados pueden revisar el uso en el Centro de partners.

- [Cambio de tamaño de VM de Microsoft Azure para el uso de reserva máximo](https://docs.microsoft.com/partner-center/azure-usage)

::: zone-end

## <a name="resize-a-storage-account"></a>Cambio de tamaño de una cuenta de almacenamiento

1. Vaya a **Cuentas de almacenamiento**.
1. Seleccione la cuenta de almacenamiento deseada.
1. Seleccione **Configurar** y ajuste las propiedades de la cuenta de almacenamiento para que coincidan con sus requisitos.
1. Seleccione **Guardar**.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Storage%2FStorageAccounts]" submitText="Go to Storage Accounts" :::

::: zone-end

## <a name="resize-a-sql-database"></a>Cambio de tamaño de una base de datos SQL

1. Vaya a **Base de datos SQL** o a **Servidores SQL** y, a continuación, seleccione el servidor.
1. Seleccione la base de datos deseada.
1. Seleccione **Configurar** y el nuevo tamaño de nivel de servicio deseado.
1. Seleccione **Aplicar**.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Sql%2FServers%2FDatabases]" submitText="Go to SQL Databases" :::

::: zone-end

# <a name="cost-management"></a>[Cost Management](#tab/ManageCost)

Es importante realizar revisiones y análisis de costos continuos. Este esfuerzo le permite tener la oportunidad de cambiar el tamaño de los recursos según sea necesario para equilibrar el costo y la carga de trabajo.

Azure Cost Management funciona con Azure Advisor para proporcionar recomendaciones de optimización de costos. Azure Advisor le ayuda a optimizar y mejorar la eficiencia mediante la identificación de recursos inactivos e infrautilizados.

1. Seleccione **Administración de costos + facturación**.
1. Seleccione **Recomendaciones de Advisor** y la pestaña **Costos**.
1. Use **Impacto** y **Ahorro potencial anual** para revisar las posibles ventajas.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/Microsoft_Azure_Billing/ModernBillingMenuBlade/Overview]" submitText="Go to Cost Management + Billing" :::

::: zone-end

También puede usar **Advisor** y seleccionar la pestaña **Costos** para identificar recomendaciones para posibles reducciones de costos.

> [!TIP]
> En el caso de los servicios que no requieren disponibilidad continua, la implementación de una solución para iniciar, detener o pausar el servicio según sea necesario puede ayudar a administrar el costo (por ejemplo, Azure Virtual Machines o Azure SQL Data Warehouse).
>

::: zone target="chromeless"

::: form action="OpenBlade[#blade/Microsoft_Azure_Expert/AdvisorBlade]" submitText="Go to Azure Advisor" :::

::: zone-end

::: zone target="docs"

- [Tutorial: Optimización de los costos a partir de las recomendaciones](https://docs.microsoft.com/azure/cost-management-billing/costs/tutorial-acm-opt-recommendations)
- [Prevención de cargos inesperados con la administración de costos y facturación de Azure](https://docs.microsoft.com/azure/billing/billing-getting-started)
- [Explore y analice los costos con Análisis de costos](https://docs.microsoft.com/azure/cost-management/quick-acm-cost-analysis)

::: zone-end
