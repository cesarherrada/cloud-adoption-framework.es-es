---
title: Niveles de administración en la administración en la nube
description: Aprenda a restringir las opciones de administración en la nube a un conjunto coherente de procesos y herramientas que pueda ofrecer a las cargas de trabajo hospedadas en la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 18a75ed46e247394aadc0caccd53988314553bcf
ms.sourcegitcommit: 0ea426f2f471eb7310c6f09478be1306cf7bf0d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "78341426"
---
# <a name="management-leveling-across-cloud-management-disciplines"></a>Nivelación de la administración entre las materias de administración de la nube

Las claves de una administración adecuada en cualquier entorno son la coherencia y los procesos repetibles. Hay infinitas opciones para las tareas que se pueden hacer en Azure. Del mismo modo, hay innumerables estrategias de administración de la nube. Para proporcionar coherencia y repetibilidad, es importante restringir esas opciones a un conjunto coherente de herramientas y procesos de administración que se ofrecerán para las cargas de trabajo hospedadas en la nube.

## <a name="suggested-management-levels"></a>Niveles de administración sugeridos

Dado que las cargas de trabajo de la cartera de TI varían, no es probable que un solo nivel de administración sea suficiente para todas ellas. Para ayudar a admitir diversas cargas de trabajo y distintos compromisos empresariales, se recomienda que los equipos de operaciones de la nube y de la plataforma establezcan algunos niveles de administración de operaciones.

![Gestión de los niveles de administración y madurez en Cloud Adoption Framework](../../_images/manage/cloud-management-maturity.png)

Como punto de partida, considere la posibilidad de establecer los niveles de administración que se muestran en el diagrama anterior y que se sugieren en la lista siguiente:

- **Base de referencia de administración:** una base de referencia de administración de la nube (o base de referencia de administración) es el conjunto definido de herramientas, procesos y precios coherentes que sirven de base para toda la administración de la nube en Azure. Para establecer una base de referencia de administración de la nube y determinar las herramientas que se incluirán en la oferta de base de referencia para su empresa, revise la lista de la sección "Materias de administración de la nube".
- **Base de referencia mejorada:** puede que varias cargas de trabajo requieran mejoras de la base de referencia que no son necesariamente específicas de una sola plataforma o carga de trabajo. Aunque estas mejoras no son rentables para todas las cargas de trabajo, debe haber procesos, herramientas y soluciones comunes para cualquier carga de trabajo que pueda justificar los costos de permitir administración adicional.
- **Especialización de la plataforma:** en cualquier entorno proporcionado, distintas cargas de trabajo utilizan algunas plataformas comunes. Estos elementos comunes de la arquitectura general no cambian cuando las empresas adoptan la nube. La especialización de la plataforma es un nivel elevado de administración que aplica los datos y la experiencia en materia de arquitectura para proporcionar un mayor nivel de administración operativa. Algunos ejemplos de especialización de la plataforma incluirían funciones de administración específicas de SQL Server, contenedores, Active Directory u otros servicios que se pueden administrar mejor mediante procesos, herramientas y arquitecturas coherentes y repetibles.
- **Especialización de la carga de trabajo:** en el caso de las cargas de trabajo realmente críticas, los costos de profundizar aún más en la administración de esa carga de trabajo pueden estar justificados. La especialización de la carga de trabajo aplica la telemetría de las cargas de trabajo para determinar estrategias más avanzadas para la administración diaria. Esos mismos datos a menudo identifican mejoras en la automatización, la implementación y el diseño que llevarán a una mayor estabilidad, confiabilidad y resistencia más allá de lo que es posible con la administración operativa por sí sola.
- **No admitidas:** igual de importante es comunicar los procesos de administración comunes que no se facilitarán mediante materias de administración de la nube en las cargas de trabajo clasificadas como no admitidas o no críticas.

Las organizaciones también pueden optar por [subcontratar las funciones relacionadas con uno o varios de estos niveles de administración a un proveedor de servicios](https://www.microsoft.com/cloud-adoption-framework-offers?ot=manage). Estos proveedores de servicios pueden usar [Azure Lighthouse](https://azure.com/lighthouse) para proporcionar una mayor precisión y transparencia.

En el resto de artículos de esta serie se describe una serie de procesos que se encuentran normalmente en cada una de estas materias.
Al mismo tiempo, la [guía de administración de Azure](../azure-management-guide/index.md) muestra las herramientas que puede admitir cada uno de estos procesos. Si necesita ayuda para crear la base de referencia de administración, comience con la guía de administración de Azure. Una vez establecida la base de referencia, esta serie de artículos y los procedimientos recomendados que los acompañan pueden ayudarle a ampliarla para definir otros niveles de asistencia de la administración.

## <a name="cloud-management-disciplines"></a>Materias de administración de la nube

Cada nivel de administración sugerido puede invocar una variedad de disciplinas de administración de la nube. Sin embargo, la asignación está diseñada para que sea más fácil encontrar las herramientas y los procesos sugeridos que se deben ofrecer en el nivel adecuado de administración de la nube.

En la mayoría de los casos, el *nivel de base de referencia de administración* descrito anteriormente se compone de procesos y herramientas de las siguientes materias. En cada caso, se resaltan algunos procesos y herramientas para demostrar las *funciones de base de referencia mejoradas*.

- **Inventario y visibilidad:** la base de referencia de administración debe incluir como mínimo un medio para realizar el inventario de los recursos y crear visibilidad sobre el estado de ejecución de cada uno.
- **Cumplimiento operativo:** la administración normal de la configuración, el tamaño, el costo y el rendimiento de los recursos es vital para mantener las expectativas de rendimiento y una línea de base de administración.
- **Protección y recuperación:** minimizar las interrupciones operativas y agilizar la recuperación puede ayudar a evitar pérdidas de rendimiento e impactos en los ingresos. La detección y la recuperación son aspectos esenciales de esta materia en cualquier línea de base de administración.

El nivel de especialización de la plataforma de la administración se extrae de los procesos y las herramientas que se alinean con las materias de operaciones de la plataforma. Del mismo modo, el nivel de especialización de la carga de trabajo de la administración se extrae de los procesos y las herramientas que se alinean con las materias de operaciones de la carga de trabajo.

## <a name="next-steps"></a>Pasos siguientes

El siguiente paso en la definición de cada nivel de administración de la nube es entender el [inventario y la visibilidad](./inventory.md).

> [!div class="nextstepaction"]
> [Opciones de inventario y visibilidad](./inventory.md)
