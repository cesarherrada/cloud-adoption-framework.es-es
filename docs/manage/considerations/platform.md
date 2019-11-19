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
ms.openlocfilehash: 6a2cf644a7c046dfb62f6049c2eae6b283e6552b
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73565074"
---
# <a name="platform-operations-in-cloud-management"></a>Operaciones de plataforma en administración de la nube

Una base de referencia de administración de la nube que abarca [inventario y visibilidad](./inventory.md), [cumplimiento operativo](./operational-compliance.md) y [protección y recuperación](./protect.md) puede proporcionar un nivel suficiente de administración de la nube para la mayoría de las cargas de trabajo de la cartera de TI. Sin embargo, esa base de referencia rara vez es suficiente para la cartera completa. Este artículo se basa en el siguiente paso más común de la administración de la nube, las operaciones de cartera.

Un estudio rápido de los recursos de la cartera de TI resalta los patrones que se admiten en las cargas de trabajo. Dentro de esas cargas de trabajo, habrá varias plataformas comunes. En función de las decisiones técnicas anteriores de la empresa, esas plataformas pueden variar considerablemente.

En algunas organizaciones habrá una gran dependencia de SQL Server, Oracle u otras plataformas de datos de código abierto. En otras organizaciones, los puntos en común se pueden originar en las plataformas host de las máquinas virtuales (VM) o los contenedores. Otras pueden tener una dependencia común de aplicaciones o sistemas de planeamiento de recursos empresariales (ERP), como SAP, Oracle u otros.

La comprensión de estos puntos en común permite al equipo de administración de la nube especializarse en niveles superiores de soporte para esas plataformas prioritarias.

## <a name="establish-a-service-catalog"></a>Establecimiento de un catálogo de servicios

El objetivo de las operaciones de plataforma es crear soluciones confiables y repetibles que el equipo de adopción de la nube pueda utilizar para ofrecer una plataforma que proporcione un mayor nivel de compromiso empresarial. Ese compromiso puede reducir la probabilidad o la frecuencia del tiempo de inactividad, lo cual mejoraría la confiabilidad. Si se produjera un error del sistema, el compromiso también podría ayudar a reducir la pérdida de datos o el tiempo de recuperación. Este compromiso suele incluir las operaciones centralizadas en curso para que se admita la plataforma.

A medida que el equipo de administración de la nube va estableciendo mayores grados de administración operativa y especialización relacionada con plataformas específicas, esas plataformas se van agregando a un catálogo de servicios creciente. El catálogo de servicios proporciona una implementación de autoservicio de las plataformas en una configuración específica, que se adhiere a las operaciones de plataforma en curso. Durante la conversación de alineación empresarial, los equipos de administración de la nube y de estrategia en la nube pueden proponer soluciones de catálogo de servicios como una forma de mejorar los compromisos de confiabilidad, tiempo de actividad y recuperación de la empresa en un proceso controlado y repetible.

Como referencia, algunas organizaciones se refieren a una primera fase del catálogo de servicios como _lista aprobada_. La principal diferencia es que un catálogo de servicios incluye compromisos operativos continuos del centro de excelencia en la nube (CCoE). Una lista aprobada es similar, ya que proporciona una lista aprobada previamente de soluciones que un equipo puede usar en la nube. Sin embargo, normalmente no existe ninguna ventaja operativa asociada a las aplicaciones en una lista aprobada.

Al igual que el debate entre el equipo de TI central y el centro de excelencia de la nube (CCoE), la diferencia es una de las prioridades. Un catálogo de servicios es una buena opción que proporciona contenciones operativas, de gobernanza y de seguridad que aceleran la innovación. Una lista aprobada dificulta la innovación hasta que la solución traspasa las puertas de las operaciones, el cumplimiento y la seguridad. Ambas soluciones son viables, pero requieren que la empresa tome decisiones de priorización ingeniosas para invertir más en innovación o en cumplimiento.

### <a name="build-the-service-catalog"></a>Creación del catálogo de servicios

La administración de la nube rara vez se realiza correctamente si se entrega un catálogo de servicios en un silo. El correcto desarrollo del catálogo requiere un asociación en el equipo de TI central o el CCoE. Este enfoque tiende a ser más satisfactorio cuando una organización de TI alcanza un nivel de madurez de CCoE, pero podría implementarse antes.

Al crear el catálogo de servicios dentro de un modelo de CCoE, el equipo de plataforma en la nube crea la plataforma de estado deseada. Los equipos de gobernanza y de seguridad en la nube validan la gobernanza y el cumplimiento en la implementación. El equipo de administración de la nube establece las operaciones en curso para esa plataforma. Asimismo, el equipo de automatización en la nube empaqueta la plataforma para una implementación escalable y repetible.

Después de empaquetar la plataforma, el equipo de administración de la nube puede agregarla al catálogo de servicios creciente. A partir de ahí, el equipo de adopción de la nube puede usar ese paquete u otros del catálogo durante la implementación. Cuando la solución pasa a producción, la empresa obtiene las ventajas adicionales de la administración operativa mejorada y una posible reducción de las interrupciones empresariales.

> [!NOTE]
> La creación de un catálogo de servicios requiere una gran cantidad de esfuerzo y tiempo de varios equipos. El uso del catálogo de servicios o la lista aprobada como mecanismo de canalización ralentiza la innovación. Cuando la innovación es una prioridad, los catálogos de servicios deben desarrollarse en paralelo a otras labores de adopción.

## <a name="define-your-own-platform-operations"></a>Definición de operaciones de plataforma propias

Aunque las herramientas y los procesos de administración pueden ayudar a mejorar las operaciones de la plataforma, a menudo no es suficiente para lograr los estados deseados de estabilidad y confiabilidad. Las verdaderas operaciones de la plataforma requieren una atención especial en los fundamentos de calidad de la arquitectura. Cuando una plataforma justifica una inversión mayor en las operaciones, se deben tener en cuenta los cinco fundamentos siguientes para que la plataforma pase a ser parte de cualquier catálogo de servicios:

- **Escalabilidad:** La capacidad de un sistema para controlar el aumento de la carga.
- **Disponibilidad:** proporción de tiempo que un sistema es funcional y está en funcionamiento.
- **Resistencia:** La capacidad de un sistema de recuperarse de los errores y seguir funcionando.
- **Administración:** procesos de operaciones que mantienen un sistema ejecutándose en producción.
- **Seguridad:** Protección de las aplicaciones y los datos frente a amenazas.

El [marco de la arquitectura de Azure](https://docs.microsoft.com/azure/architecture/guide/pillars) proporciona un enfoque para evaluar cargas de trabajo específicas para el cumplimiento de estos fundamentos con el fin de mejorar las operaciones generales. Estos fundamentos se pueden aplicar tanto a las operaciones de la plataforma como a las de la carga de trabajo.

## <a name="get-started-with-specific-platforms"></a>Introducción a las plataformas específicas

Las plataformas que se tratan en las secciones siguientes son comunes para los clientes típicos de Azure. Además, pueden justificar fácilmente una inversión en operaciones de la plataforma. Los equipos de administración de la nube tienden a comenzar por estas al elaborar los requisitos de las operaciones de la plataforma o el catálogo de servicios completo.

### <a name="paas-data-operations"></a>Operaciones de datos de PaaS

Los datos suelen ser los primeros en considerarse para justificar las inversiones en operaciones de plataforma. Cuando se hospedan datos en un entorno de plataforma como servicio (PaaS), las partes interesadas de la empresa tienden a solicitar un objetivo de punto de recuperación (RPO) reducido para minimizar la pérdida de datos. En función de la naturaleza de la aplicación, también pueden solicitar una reducción del objetivo de tiempo de recuperación (RTO). En cualquier caso, la arquitectura que admite soluciones de datos basadas en PaaS puede fácilmente dar cabida a un mayor nivel de soporte de administración.

En la mayoría de los escenarios, el costo de mejorar los compromisos de administración se justifica fácilmente, incluso para las aplicaciones que no son críticas. Esta mejora de las operaciones de la plataforma es tan común que muchos equipos de administración de la nube la ven más como una base de referencia mejorada que como una verdadera mejora de las operaciones de la plataforma.

### <a name="iaas-data-operations"></a>Operaciones con datos de IaaS

Cuando los datos se hospedan en una solución de infraestructura como servicio (IaaS) tradicional, el esfuerzo para mejorar el RTO y el RPO puede ser mucho mayor. Sin embargo, el deseo de las partes interesadas de la empresa por lograr mejores compromisos de administración apenas se ve afectado por la decisión de elegir PaaS o IaaS. Si acaso, la comprensión de las diferencias fundamentales en la arquitectura puede instar a la empresa a solicitar soluciones de PaaS o compromisos que coincidan con el contenido disponible en las soluciones de PaaS. La modernización de cualquier plataforma de datos de IaaS se debe considerar como primer paso a las operaciones de plataforma.

Cuando la modernización no es una opción, los equipos de administración de la nube suelen priorizar las plataformas de datos basadas en IaaS como primer servicio necesario en el catálogo. Proporcionar a la empresa una opción entre servidores de datos independientes y soluciones de datos agrupadas de alta disponibilidad facilita en gran medida la conversación sobre el compromiso de la empresa. Una descripción básica de las mejoras operativas y el aumento de los costos dará a la empresa las armas necesarias para tomar la mejor decisión respecto a los procesos empresariales y las cargas de trabajo de soporte.

### <a name="other-common-platform-operations"></a>Otras operaciones de plataforma comunes

Además de las plataformas de datos, los hosts de máquina virtual suelen ser una plataforma común para las mejoras en las operaciones. Normalmente, los equipos de administración de la nube y la plataforma en la nube invierten en mejoras en los hosts o las soluciones de contenedor de VMware. Dichas inversiones pueden mejorar la estabilidad y la confiabilidad de los hosts, que admiten las VM, que a su vez impulsan las cargas de trabajo. Las operaciones adecuadas en un host o contenedor pueden mejorar el RPO o el RTO de varias cargas de trabajo. Este enfoque crea mejores compromisos empresariales, al tiempo que distribuye la inversión. Los compromisos mejorados y los costos reducidos se combinan para facilitar enormemente la justificación de las mejoras en las operaciones de la plataforma y de administración de la nube.

## <a name="next-steps"></a>Pasos siguientes

En paralelo con las mejoras en las operaciones de plataforma, los equipos de administración de la nube también se centran en mejorar las [operaciones de carga de trabajo](./workload.md) para las cargas de trabajo de producción del 20 % o menos.

> [!div class="nextstepaction"]
> [Mejora de las operaciones de carga de trabajo](./workload.md)
