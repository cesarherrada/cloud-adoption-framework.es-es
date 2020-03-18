---
title: Configuración de alertas básicas
description: Aprenda a usar los servicios de administración de servidores de Azure para configurar alertas y notificaciones que ayuden a los equipos de TI a mantenerse informados de los problemas que se produzcan.
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 3525b8d84ee6dd54072a4fed401114578de7fcb3
ms.sourcegitcommit: 959cb0f63e4fe2d01fec2b820b8237e98599d14f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "79094468"
---
# <a name="set-up-basic-alerts"></a>Configuración de alertas básicas

Una parte clave de la administración de recursos es la recepción de notificaciones cuando se producen problemas; Las alertas notifican proactivamente las condiciones críticas en función de los desencadenadores de las métricas, los registros o los problemas de estado del servicio. Como parte de la incorporación a los servicios de administración de servidores de Azure, puede configurar alertas y notificaciones que ayuden a los equipos de TI a mantenerse informados de los problemas que se produzcan.

## <a name="azure-monitor-alerts"></a>Alertas de Azure Monitor

Azure Monitor ofrece funcionalidades de [alerta](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview) para enviar notificaciones por correo electrónico o mensajería cuando se producen errores. Estas funcionalidades se basan en una plataforma común de supervisión de datos que incluye registros y métricas generados por los servidores y otros recursos. Un conjunto de herramientas común de Azure Monitor le permite analizar los datos combinados procedentes de varios recursos y usarlos para desencadenar alertas. Estos desencadenadores pueden incluir:

- Valores de métrica
- Consultas de búsqueda de registros
- Eventos del registro de actividad
- Estado de la plataforma Azure subyacente
- Pruebas de disponibilidad del sitio web

Consulte la [lista de orígenes de datos de Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources) para obtener una descripción más detallada de los orígenes de los datos de supervisión que recopila este servicio.

Para más información sobre la creación y la administración manuales de alertas mediante Azure Portal, consulte la [documentación de Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-metric).

## <a name="automated-deployment-of-recommended-alerts"></a>Implementación automatizada de alertas recomendadas

En esta guía se recomienda crear un conjunto de 15 alertas para la supervisión básica de la infraestructura. Los scripts de implementación se encuentran en el [kit de herramientas de alerta de Azure del repositorio de GitHub](https://github.com/Microsoft/manageability-toolkits).

Este paquete crea alertas de:

- Espacio de disco bajo
- Poca memoria disponible
- Uso elevado de CPU
- Cierres inesperados
- Sistemas de archivos dañados
- Errores de hardware comunes

El paquete usa hardware de servidor de HP como ejemplo. Cambie la configuración del archivo de configuración asociado para reflejar su hardware OEM. También puede agregar más contadores de rendimiento al archivo de configuración. Para implementar el paquete, ejecute el archivo New-CoreAlerts.ps1.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre las operaciones y los mecanismos de seguridad que admiten las operaciones en curso.

> [!div class="nextstepaction"]
> [Administración y seguridad en curso](./ongoing-management-overview.md)
