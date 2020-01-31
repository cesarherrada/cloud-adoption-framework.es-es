---
title: Protección, supervisión y administración de recursos
description: Protección de las herramientas de administración y supervisión
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 5e0267c5b15e01b9f53e76ba2bc16f95381f81aa
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76801280"
---
# <a name="secure-monitoring-and-management-tools"></a>Protección de las herramientas de administración y supervisión

Una vez completada la migración, los recursos migrados deben administrarse mediante operaciones de TI controladas. Este artículo no representa una desviación de los procedimientos recomendados. Por el contrario, lo siguiente debe considerarse como un producto mínimamente viable para la protección y administración de los recursos migrados, ya sea desde las operaciones de TI o de forma independiente cuando estas operaciones se conecten.

## <a name="monitoring"></a>Supervisión

La *supervisión* es el acto de recopilar y analizar datos para determinar el rendimiento, el mantenimiento y la disponibilidad de su carga de trabajo empresarial y de los recursos de los que esta depende. Azure incluye varios servicios que realizan individualmente una tarea o un rol específico en el espacio de supervisión. Juntos, estos servicios ofrecen una solución completa para recopilar, analizar y actuar en la telemetría de las aplicaciones de la carga de trabajo y los recursos de Azure que las admiten. Obtenga visibilidad sobre el estado de mantenimiento y el rendimiento de sus aplicaciones, infraestructura y datos en Azure con herramientas de supervisión en la nube como Azure Monitor, Log Analytics y Application Insights. Use estas herramientas de supervisión en la nube para tomar medidas e intégrelas con sus soluciones de administración de servicios:

- **Supervisión básica.** La supervisión básica proporciona el control fundamental requerido de los recursos de Azure. Estos servicios requieren una configuración mínima y recopilan la telemetría principal que usan los servicios de supervisión premium.
- **Supervisión profunda de la aplicación y la infraestructura.** Los servicios de Azure proporcionan funcionalidades enriquecidas para recopilar y analizar datos de supervisión en profundidad. Estos servicios se basan en la supervisión básica y aprovechan las funcionalidades comunes de Azure. Proporcionan análisis eficaces con los datos recopilados y le ofrecen información única sobre sus aplicaciones e infraestructura.

Obtenga más información sobre [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) para la supervisión de los recursos migrados.

## <a name="security-monitoring"></a>Supervisión de la seguridad

Confíe en Azure Security Center para lograr una supervisión unificada de la seguridad y obtener notificaciones de amenazas avanzadas de las cargas de trabajo de su nube híbrida. Security Center aporta visibilidad total y control sobre la seguridad de sus aplicaciones en la nube de Azure. Detecte posibles amenazas y tome medidas con rapidez, y reduzca su exposición mediante la protección contra amenazas adaptable. El panel integrado proporciona información instantánea sobre alertas de seguridad y vulnerabilidades que requieren atención. Azure Security Center puede ayudarle con muchas funciones, incluidas:

- **Supervisión centralizada de directivas.** Garantice el cumplimiento de los requisitos de seguridad normativos o de la empresa administrando las directivas de seguridad de forma centralizada de las cargas de trabajo en la nube híbridas.
- **Evaluación continua de la seguridad.** Supervise la seguridad de máquinas, redes, almacenamiento y servicios de datos y aplicaciones para detectar posibles problemas de seguridad.
- **Recomendaciones prácticas.** Corrija las vulnerabilidades de seguridad antes de que los atacantes se aprovechen. Incluya recomendaciones de seguridad prácticas y prioritarias.
- **Defensas avanzadas en la nube.** Reduzca las amenazas con acceso Just-In-Time a los puertos de administración y la creación de listas seguras para controlar las aplicaciones que se ejecutan en las máquinas virtuales.
- **Alertas e incidentes clasificados por orden de prioridad.** Céntrese primero en las amenazas más críticas con la clasificación en orden de prioridad de las alertas e incidentes de seguridad.
- **Soluciones de seguridad integradas.** Recopile, busque y analice datos de seguridad de una gran variedad de orígenes, incluidas las soluciones conectadas de los asociados.

Obtenga más información sobre [Azure Security Center](https://docs.microsoft.com/azure/security-center) para la protección de los recursos migrados.

## <a name="service-health-monitoring"></a>Supervisión del estado del servicio

Azure Service Health le proporciona alertas e indicaciones personalizadas cuando le afectan los incidentes que se producen en los servicios de Azure. Puede enviarle notificaciones, ayudarle a conocer el impacto de los problemas e informarle de la resolución de estos. También le puede ayudar a preparar las operaciones de mantenimiento y los cambios planeados que podrían afectar a la disponibilidad de sus recursos.

- **Panel de estado del servicio.** Compruebe el estado general de los servicios y regiones de Azure, con actualizaciones detalladas sobre los problemas de servicio actuales, próximos mantenimientos planeados y transiciones de servicio.
- **Alertas del estado del servicio.** Configure alertas que le notifiquen a usted y a sus equipos en caso de un problema de servicio como una interrupción o un próximo mantenimiento planeado.
- **Historial de estados de servicio.** Revise los problemas de servicio pasados y descargue resúmenes e informes oficiales de Microsoft.

Obtenga más información acerca de [Azure Service Health](https://docs.microsoft.com/azure/service-health) para mantenerse informado sobre el estado de los recursos migrados.

## <a name="protect-assets-and-data"></a>Protección de recursos y datos

Azure Backup proporciona un medio de protección de las máquinas virtuales, archivos y datos. Azure Backup puede ayudarle con muchas funciones, incluidas:

- La copia de seguridad de máquinas virtuales.
- La copia de seguridad de archivos.
- La copia de seguridad de bases de datos de SQL Server.
- La recuperación de recursos protegidos.

Obtenga más información sobre [Azure Backup](https://docs.microsoft.com/azure/backup) para proteger los recursos migrados.

## <a name="optimize-resources"></a>Optimización de recursos

Azure Advisor es su guía personalizada de procedimientos recomendados para Azure. Azure Advisor analiza sus configuraciones y la telemetría de uso y ofrece recomendaciones que le ayudan a optimizar los recursos de Azure para obtener alta disponibilidad, seguridad, rendimiento y rentabilidad. Las acciones insertadas de Advisor le ayudan a corregir sus recomendaciones de forma rápida y sencilla, así como a optimizar las implementaciones.

- **Procedimientos recomendados de Azure.** Optimice los recursos migrados para lograr una alta disponibilidad, seguridad, rendimiento y rentabilidad.
- **Guía paso a paso.** Obtenga recomendaciones de corrección eficaces con vínculos rápidos guiados.
- **Nuevas alertas de recomendaciones.** Manténgase al día sobre nuevas recomendaciones como, por ejemplo, oportunidades adicionales para ajustar el tamaño de las máquinas virtuales y ahorrar dinero.

Obtenga más información sobre el uso de [Azure Advisor](https://docs.microsoft.com/azure/advisor/advisor-overview) para optimizar los recursos migrados.

## <a name="suggested-skills"></a>Aptitudes sugeridas

Microsoft Learn es un enfoque nuevo al aprendizaje. La preparación para las nuevas aptitudes y responsabilidades que acompañan a la adopción de la nube no es fácil. Microsoft Learn proporciona un enfoque más gratificante para el aprendizaje práctico que le ayuda a lograr sus objetivos con más rapidez. Gane puntos y niveles y consiga más.

Este es un ejemplo de ruta de aprendizaje adaptada de Microsoft Learn que está alineada con la parte segura y de administración de Cloud Adoption Framework: 

[Proteja los datos en la nube](https://docs.microsoft.com/learn/paths/secure-your-cloud-data/): Azure se diseñó para la seguridad y el cumplimiento. Aprenda a aprovechar los servicios integrados para almacenar los datos de las aplicaciones de forma segura para asegurarse de que solo tienen acceso a ellos los servicios y clientes autorizados.
