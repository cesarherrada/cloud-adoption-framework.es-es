---
title: 'Operaciones de plataforma: administración y operaciones en la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Operaciones de plataforma: administración y operaciones en la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: ca62f35c059e185850bb47045fa0edef7be1d223
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683592"
---
# <a name="platform-operations-in-cloud-management"></a>Operaciones de plataforma en administración de la nube

Una base de referencia de administración de la nube que abarca [inventario y visibilidad](./inventory.md), [cumplimiento operativo](./operational-compliance.md) y [protección y recuperación](./protect.md) puede proporcionar un nivel suficiente de administración de la nube para la mayoría de las cargas de trabajo de la cartera de TI. Sin embargo, esto rara vez es suficiente para la cartera completa. Este artículo se basa en el siguiente paso más común de la administración de la nube, las operaciones de cartera.

Un estudio rápido de los recursos de la cartera de TI resaltará patrones admitidos en las cargas de trabajo. Dentro de esas cargas de trabajo, habrá varias plataformas comunes. En función de las decisiones técnicas anteriores de la empresa, esas plataformas podrían ser muy diferentes. En algunas organizaciones habrá una gran dependencia de SQL Server, Oracle u otras plataformas de datos de código abierto. En otras, los puntos en común se pueden originar en las plataformas host de las máquinas virtuales o los contenedores. Otras pueden tener una dependencia común de aplicaciones o sistemas de planeamiento de recursos empresariales (ERP) como SAP, Oracle u otros.

La comprensión de estos puntos en común permite al equipo de administración de la nube especializarse en niveles superiores de soporte para esas plataformas prioritarias.

## <a name="establish-a-service-catalog"></a>Establecimiento de un catálogo de servicios

El objetivo de las operaciones de plataforma es crear soluciones confiables y repetibles que un equipo de adopción de la nube pueda aprovechar para ofrecer una plataforma que proporcione mayor nivel de compromiso empresarial. Ese compromiso puede reducir la probabilidad o la frecuencia del tiempo de inactividad, lo cual mejoraría la confiabilidad. El compromiso también puede reducir la pérdida de datos o el tiempo de recuperación en caso de que se produzca un error en el sistema. Este compromiso suele incluir las operaciones en curso y centralizadas para que se admita la plataforma.

A medida que el equipo de administración de la nube va estableciendo mayores grados de administración operativa y especialización relacionada con plataformas específicas, esas plataformas se van agregando a un catálogo de servicios creciente. Ese catálogo de servicios proporciona una implementación autoservicio de las plataformas en una configuración específica que se adhiere a las operaciones de plataforma en curso. Durante la conversación de alineación empresarial, los equipos de administración de la nube y de estrategia en la nube pueden proponer soluciones de catálogo de servicios como una forma de mejorar los compromisos de confiabilidad, tiempo de actividad y recuperación de la empresa en un proceso controlado y repetible.

Como referencia, algunas organizaciones se referirán a una primera fase del catálogo de servicios como "lista aprobada". La principal diferencia es que un catálogo de servicios incluye compromisos operativos continuos del centro de excelencia en la nube. Una "lista aprobada" es parecida, ya que proporciona una lista preaprobada de soluciones que un equipo puede usar en la nube, pero no suele traer asociadas ventajas operativas a las aplicaciones. Al igual que el debate entre el equipo de TI central y el centro de excelencia de la nube (CCoE), la diferencia es una de las prioridades. Un catálogo de servicios es una buena opción que proporciona contenciones operativas, de gobernanza y de seguridad que aceleran la innovación. Una "lista aprobada" dificulta la innovación hasta que la solución traspasa las puertas de las operaciones, el cumplimiento y la seguridad. Ambas son soluciones viables, pero requieren que la empresa priorice minuciosamente para invertir más en innovación o en cumplimiento.

### <a name="building-the-service-catalog"></a>Creación del catálogo de servicios

La administración de la nube rara vez se realiza correctamente si se entrega un catálogo de servicios en un silo. El correcto desarrollo del catálogo requiere la asociación dentro el equipo de TI central o el centro de excelencia de la nube (CCoE). Este enfoque tiende a ser más satisfactorio cuando una organización de TI alcanza un nivel de madurez de CCoE, pero podría implementarse antes.

Al crear el catálogo de servicios dentro de un modelo de CCoE, el equipo de plataforma en la nube crea la plataforma de estado deseada. Los equipos de gobernanza y de seguridad en la nube validan la gobernanza y el cumplimiento en la implementación. El equipo de administración de la nube establece las operaciones en curso para esa plataforma. El equipo de automatización en la nube empaqueta la plataforma para una implementación escalable y repetible.

Una vez empaquetada, el equipo de administración de la nube puede agregar el paquete al catálogo de servicios creciente. A partir de ahí, el equipo de adopción de la nube puede aprovechar ese paquete u otros del catálogo durante la implementación. Con la solución en producción, la empresa obtiene las ventajas adicionales de la administración operativa mejorada y la posible reducción en las interrupciones empresariales.

> [!NOTE]
> La creación de un catálogo de servicios requiere una gran cantidad de esfuerzo y tiempo de varios equipos. El uso del catálogo de servicios o la lista de permitidos como mecanismo de canalización ralentiza la innovación. Cuando la innovación es una prioridad, los catálogos de servicios deben desarrollarse en paralelo a otras labores de adopción.

## <a name="defining-your-own-platform-operations"></a>Definición de operaciones de plataforma propias

Las herramientas y los procesos de administración pueden mejorar las operaciones de plataforma. Pero esto no suele ser suficiente para lograr el estado deseado de estabilidad y confiabilidad. Las verdaderas operaciones de plataforma requieren atención especial en los fundamentos de calidad de la arquitectura. Cuando una plataforma justifica una inversión mayor en las operaciones, se deben tener en cuenta los cinco fundamentos siguientes para que la plataforma pase a ser parte de cualquier catálogo de servicios:

1. Escalabilidad: La capacidad de un sistema para controlar el aumento de la carga.
2. Disponibilidad: La proporción de tiempo que un sistema es funcional y está en funcionamiento.
3. Resistencia: La capacidad de un sistema de recuperarse de los errores y seguir funcionando.
4. Administración: Procesos de operaciones que mantienen un sistema ejecutándose en producción.
5. Seguridad: Protección de las aplicaciones y los datos frente a amenazas.

El [marco de la arquitectura de Azure](https://docs.microsoft.com/azure/architecture/guide/pillars) proporciona un enfoque para evaluar cargas de trabajo específicas para el cumplimiento de estos fundamentos con el fin de mejorar las operaciones generales. Estos fundamentos se pueden aplicar tanto a las operaciones de la plataforma como a las de la carga de trabajo.

## <a name="getting-started-with-specific-platforms"></a>Introducción a las plataformas específicas

Para los clientes típicos de Azure, a continuación se muestran plataformas comunes que pueden justificar fácilmente una inversión en operaciones de plataforma. Los equipos de administración de la nube tienden a comenzar por estas al elaborar los requisitos de las operaciones de la plataforma o el catálogo de servicios completo.

### <a name="paas-data-operations"></a>Operaciones de datos de PaaS

Los datos suelen ser los primeros en considerarse para justificar las inversiones en operaciones de plataforma. Cuando se hospedan en un entorno de plataforma como servicio (PaaS), las partes interesadas de la empresa tienden a solicitar un objetivo del punto de recuperación (RPO) reducido para minimizar la pérdida de datos. En función de la naturaleza de la aplicación, también pueden solicitar una reducción del objetivo del tiempo de recuperación (RTO). En cualquier caso, la arquitectura que admite soluciones de datos basadas en PaaS puede fácilmente dar cabida a un mayor nivel de soporte de administración.

En la mayoría de los escenarios, el costo de mejorar los compromisos de administración se justifica fácilmente, incluso para las aplicaciones que no son críticas. Esta mejora de las operaciones de plataforma es tan común que muchos equipos de administración en la nube la ven más como una base de referencia mejorada, en lugar de tratarla como una verdadera mejora de las operaciones de plataforma.

### <a name="iaas-data-operations"></a>Operaciones con datos de IaaS

Cuando los datos se hospedan en una solución de infraestructura como servicio (IaaS) tradicional, los esfuerzos por mejorar el RTO y el RPO pueden ser mucho mayores. Sin embargo, las partes interesadas de la empresa que desean mejores compromisos de administración apenas resultan afectadas por la decisión de elegir PaaS o IaaS. Si acaso, la comprensión de las diferencias fundamentales en la arquitectura puede instar a la empresa a solicitar soluciones de PaaS o compromisos que coincidan con lo disponible en las soluciones de PaaS. La modernización de cualquier plataforma de datos de IaaS se debe considerar como primer paso a las operaciones de plataforma.

Cuando la modernización no es una opción, los equipos de administración de la nube suelen priorizar las plataformas de datos basadas en IaaS como primer servicio necesario en el catálogo. Proporcionar a la empresa una opción entre servidores de datos independientes y soluciones de datos agrupadas y de alta disponibilidad facilita en gran medida la conversación sobre el compromiso de la empresa. Una descripción básica de las mejoras operativas y el aumento de los costos dará a la empresa las armas necesarias para tomar la mejor decisión respecto a los procesos empresariales y las cargas de trabajo de soporte.

### <a name="other-common-platform-operations"></a>Otras operaciones de plataforma comunes

Además de las plataformas de datos, los hosts de máquina virtual suelen ser una plataforma común para las mejoras en las operaciones. Normalmente, los equipos de administración de la nube y los equipos de administración de la plataforma en la nube invierten en mejoras en los hosts de VMWare o en las soluciones de contenedor para mejorar la estabilidad y confiabilidad de los hosts que admiten las máquinas virtuales y potencian las cargas de trabajo. Las operaciones adecuadas en un host o contenedor pueden mejorar el RPO/RTO de varias cargas de trabajo. Este enfoque crea mejores compromisos empresariales, al tiempo que distribuye la inversión. En conjunto, los compromisos mejorados y los costos reducidos facilitan la justificación de las mejoras en las operaciones de plataforma y la administración de la nube.

## <a name="next-steps"></a>Pasos siguientes

En paralelo con las mejoras en las operaciones de plataforma, los equipos de administración de la nube también se centrarán en mejorar las [operaciones de carga de trabajo](./workload.md) para las cargas de trabajo de producción del 20% o menos.

> [!div class="nextstepaction"]
> [Mejora de las operaciones de carga de trabajo](./workload.md)
