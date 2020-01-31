---
title: 'Compromiso empresarial: administración y operaciones en la nube'
description: 'Compromiso empresarial: administración y operaciones en la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 4827ca2aac045b105beed9c15de366311092a7f2
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76807859"
---
# <a name="business-commitment-in-cloud-management"></a>Compromiso empresarial en la administración de la nube

La definición de un _compromiso empresarial_ es un ejercicio de equilibrar prioridades. El objetivo es alinear el nivel adecuado de administración operativa con un costo operativo aceptable. La búsqueda de ese equilibrio requiere algunos puntos de datos y cálculos, que se describen en este artículo.

![Equilibrio entre costos y resistencia](../../_images/manage/business-commitment-scale.png)

Los compromisos de estabilidad empresarial, a través de la resistencia técnica u otros efectos del Acuerdo de Nivel de Servicio (SLA), son una decisión de justificación empresarial. Para la mayoría de las cargas de trabajo de un entorno, es suficiente un nivel de base de referencia de administración de la nube. Para otros, un aumento de los costos de 2x a 4x se justifica fácilmente por el posible efecto de las interrupciones en el negocio.

Los artículos anteriores de esta serie pueden ayudarle a comprender la clasificación y el impacto de las interrupciones en varias cargas de trabajo. Este artículo le ayuda a calcular los resultados. Como se muestra en la imagen anterior, cada nivel de administración de la nube tiene puntos de inflexión en los que los costos pueden aumentar más rápido que la resistencia. Esos puntos de inflexión requerirán decisiones y compromisos empresariales detallados.

## <a name="determine-a-proper-commitment-with-the-business"></a>Determinación de un compromiso adecuado con el negocio

Para cada carga de trabajo de la cartera, el equipo de operaciones en la nube y el equipo de estrategia en la nube deben alinearse en el nivel de administración que proporciona directamente el equipo de operaciones en la nube.

A medida que establece un compromiso con el negocio, existen algunos aspectos clave que se deben alinear:

- Requisitos previos de las operaciones de TI
- Responsabilidad de administración
- Inquilino en la nube
- Factores de costo indirecto
- ROI con la prevención de pérdidas
- Validación del nivel de administración

Para ayudar en el proceso de toma de decisiones, en el resto de este artículo se describe con mayor detalle cada uno de estos aspectos.

## <a name="it-operations-prerequisites"></a>Requisitos previos de las operaciones de TI

En la [Guía de administración de Azure](../azure-management-guide/index.md) se describen las herramientas de administración disponibles en Azure. Antes de llegar a un compromiso con la empresa, el departamento de TI debe determinar una línea de base de administración estándar que se aplique a todas las cargas de trabajo administradas. Después, debe calcular los costos de administración estándares para cada una de las cargas de trabajo administradas en la cartera de TI en función de la cantidad de núcleos de CPU, del espacio en disco y de otras variables relacionadas con los recursos. También estimará un Acuerdo de Nivel de Servicio compuesto para cada carga de trabajo en función de la arquitectura.

> [!TIP]
> Los equipos de operaciones de TI a menudo usan un tiempo de actividad mínimo predeterminado del 99,9 % para el Acuerdo de Nivel de Servicio compuesto inicial. También pueden optar por normalizar los costos de administración en función de la carga de trabajo media, especialmente en el caso de las soluciones con requisitos mínimos de registro y almacenamiento. Calcular el promedio de los costos de algunas cargas de trabajo de importancia intermedia puede ser un buen punto de partida para las conversaciones iniciales.

<!-- -->

> [!TIP]
> Si usa el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube, los campos de administración de las operaciones deben actualizarse para reflejar estos requisitos previos. Estos campos incluyen el _nivel de compromiso_, el _Acuerdo de Nivel de Servicio compuesto_ y el _costo mensual_. El costo mensual debe representar el costo mensual agregado de las herramientas de administración de las operaciones.

La base de referencia de administración de las operaciones sirve como punto de partida que validar en las siguientes secciones.

## <a name="management-responsibility"></a>Responsabilidad de administración

En un entorno local tradicional, los costos de administración del entorno se suelen presuponer como costos ocultos de las operaciones de TI. En la nube, la administración es una decisión intencionada con impacto presupuestario directo. Los costos de cada función de administración se pueden atribuir más directamente a cada carga de trabajo implementada en la nube. Este enfoque permite mayor control, pero exige a los equipos de operaciones en la nube y los equipos de estrategia en la nube que celebren primero en un acuerdo sobre las responsabilidades.

Las organizaciones también pueden optar por [externalizar algunas de sus funciones de administración actuales a algún proveedor de servicios](https://www.microsoft.com/cloud-adoption-framework-offers?ot=manage). Estos proveedores de servicios pueden usar [Azure Lighthouse](https://azure.com/lighthouse) para ofrecer a las organizaciones un control más preciso al conceder acceso a los recursos, además de mayor visibilidad en las acciones que realizan.

- **Responsabilidad delegada**: dado que no es necesario centralizar y adoptar una sobrecarga de administración operativa, se están pensando nuevos enfoques para las operaciones de TI de muchas organizaciones. Un enfoque típico es la _responsabilidad delegada_. En un modelo de excelencia en la nube, las operaciones y la automatización de la plataforma proporcionan herramientas de administración autoservicio que pueden usar los equipos de operaciones empresariales, independientemente de los equipos de operaciones de TI centrales. Este enfoque proporciona a las partes interesadas de la empresa un control total sobre los presupuestos relacionados con la administración. También permite al centro de excelencia de la nube (CCoE) asegurarse de que un mínimo de barreras se ha implementado correctamente. En este modelo, el equipo de TI actúa como agente y guía que ayuda a la empresa a tomar decisiones sensatas. Las operaciones empresariales supervisan las operaciones cotidianas de las cargas de trabajo dependientes.

- **Responsabilidad centralizada**: los requisitos de cumplimiento, la complejidad técnica y algunos modelos de servicios compartidos pueden requerir un modelo de _TI central_. En este modelo, el equipo de TI sigue ejerciendo las responsabilidades de administración de las operaciones. El diseño del entorno, los controles de administración y las herramientas de gobernanza se pueden administrar y controlar de forma centralizada, lo que restringe el rol de las partes interesadas de la empresa al realizar compromisos de administración. Sin embargo, la visibilidad del costo y la arquitectura de los enfoques en la nube facilitan mucho a los equipos de TI centralizados la comunicación de los costos y el nivel de administración de cada carga de trabajo.

- **Modelo mixto:** la clasificación es la esencia de un _modelo mixto_ de responsabilidades de administración. Las empresas que se encuentran en medio de una transformación de sus instalaciones locales a la nube pueden necesitar un modelo operativo local primero durante un tiempo. Las empresas con requisitos estrictos de cumplimiento o que dependen de contratos a largo plazo con proveedores externos de TI pueden necesitar un modelo operativo centralizado.

  Independientemente de sus restricciones, las empresas actuales deben innovar. En los escenarios de rápida innovación, en medio de un modelo de responsabilidad centralizada en un equipo de TI central, un enfoque de modelo mixto puede proporcionar equilibrio. En este enfoque, un equipo de TI central proporciona un modelo operativo centralizado para todas las cargas de trabajo críticas o que contienen información confidencial. Al mismo tiempo, el resto de clasificaciones de las cargas de trabajo se pueden colocar en un entorno de nube diseñado para responsabilidades delegadas. El enfoque de responsabilidad centralizada actúa como modelo operativo general. La empresa tiene flexibilidad para adoptar un modelo operativo especializado, en función del nivel de soporte y confidencialidad necesario.

El primer paso es el compromiso con un enfoque de responsabilidad, que a continuación dé forma a los siguientes compromisos.

**¿Qué organización será responsable de la administración de las operaciones diarias de esta carga de trabajo?**

## <a name="cloud-tenancy"></a>Inquilino en la nube

Para la mayoría de las empresas, la administración es más fácil cuando todos los recursos residen en un único inquilino. Sin embargo, algunas organizaciones pueden tener que mantener varios inquilinos. Para saber por qué una empresa puede requerir un entorno multiinquilino de Azure, consulte [Centralización de operaciones de administración con Azure Lighthouse](../centralize-operations.md).

**¿Residirá esta carga de trabajo en un único inquilino de Azure junto con todas las demás?**

## <a name="soft-cost-factors"></a>Factores de costo indirecto

En la siguiente sección se describe un enfoque comparativo del rendimiento en relación con los niveles de los procesos y las herramientas de administración. Al final de esta sección, cada carga de trabajo analizada mide los costos de administración en relación con el impacto previsto de las interrupciones de la empresa. Este enfoque proporciona una forma relativamente sencilla de comprender si se justifica una inversión en enfoques de administración más completos.

Antes de calcular los números, es importante examinar los factores de costo indirecto. Los factores de costo indirecto producen un rendimiento difícil de medir mediante ahorro en los costos fijos, que sería visible en un balance de pérdidas y ganancias. Los factores de costo indirecto son importantes, ya que pueden indicar una necesidad de invertir en más administración que la que sería prudente desde el punto de vista fiscal.

Estos son algunos ejemplos de factores de costo indirecto:

- Uso diario de una carga de trabajo por parte del Consejo o el consejero delegado.
- Uso de la carga de trabajo parte de un _x %_ de clientes como máximo, que provoca un mayor impacto en los ingresos en otro lugar.
- Efecto sobre la satisfacción de los empleados.

El siguiente punto de datos necesario para realizar un compromiso es una lista de los factores de costo indirecto. No es necesario documentar estos factores en esta fase, pero las partes interesadas de la empresa deben ser conscientes de la importancia de estos factores y su exclusión de los siguientes cálculos.

## <a name="calculate-loss-avoidance-roi"></a>Cálculo de la ROI con la prevención de pérdidas

Al calcular el rendimiento relativo en los costos de administración de las operaciones, el equipo de TI responsable de las operaciones en la nube debe cumplir los requisitos previos anteriores y presuponer un nivel mínimo de administración para todas las cargas de trabajo.

El siguiente compromiso que debe realizarse es una aceptación por parte de la empresa de los costos asociados con la oferta administrada según la base de referencia.

**¿Acuerda la empresa invertir en la oferta de base de referencia para cumplir los estándares mínimos de las operaciones en la nube?**

Si la empresa no está de acuerdo con ese nivel de administración, debe idearse una solución que le permita continuar sin que ello afecte de forma significativa a las operaciones en la nube de otras cargas de trabajo.

Si la empresa desea un nivel de administración superior al estándar, el resto de esta sección le ayudará a validar esa inversión y el rendimiento asociado (en forma de prevención de pérdidas).

### <a name="increased-levels-of-management-design-principles-and-service-catalog"></a>Mayores niveles de administración: principios de diseño y catálogo de servicios

En el caso de las soluciones administradas, se pueden aplicar varios principios de diseño y soluciones de plantilla además de la base de referencia de administración. Todos los principios de diseño para la confiabilidad y la resistencia suman costos operativos a la carga de trabajo. Para que el equipo de TI y la empresa acuerden estos compromisos adicionales, es importante comprender las posibles pérdidas que se pueden evitar con esa mayor inversión.

Los cálculos siguientes le guiarán por las fórmulas para comprender mejor las diferencias entre las pérdidas y el aumento de las inversiones en administración. Para obtener instrucciones sobre cómo calcular el costo de la mayor administración, consulte los artículos sobre la [automatización de la carga de trabajo](./workload.md) y la [automatización de la plataforma](./platform.md).

> [!TIP]
> Si utiliza el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube, actualice los campos de administración de las operaciones para que reflejen cada conversación. Estos campos incluyen el _nivel de compromiso_, el _Acuerdo de Nivel de Servicio compuesto_ y el _costo mensual_. El costo mensual debe representar el costo mensual de las herramientas de administración de las operaciones agregadas. Una vez actualizados, esos campos actualizarán las fórmulas del ROI y los campos siguientes.

### <a name="estimate-outage-hours-per-year"></a>Estimación de las interrupciones (horas al año)

El Acuerdo de Nivel de Servicio compuesto se basa en la implementación de cada recurso en la carga de trabajo. Ese campo controla la _interrupción estimada_ (_Est. Outage_ [Interrupción estimada] en el libro). Para calcular la interrupción estimada en horas al año sin usar el libro, aplique la siguiente fórmula:

> _Interrupción estimada = (1 - porcentaje del Acuerdo de Nivel de Servicio compuesto) x número de horas de un año_

En el libro se usa el valor predeterminado de _8760 horas al año_.

### <a name="standard-loss-impact"></a>Efecto estándar de las pérdidas

El _efecto estándar de las pérdidas_ (_Standard impact_ [Efecto estándar] en el libro) pronostica el efecto financiero de las interrupciones, suponiendo que la predicción _interrupción estimada_ resulte precisa. Para calcular esta previsión sin usar el libro, aplique la siguiente fórmula:

> _Efecto estándar = interrupción estimada @ tres novenos del tiempo de actividad x tiempo/valor del efecto_

Esto sirve como base de referencia del costo si las partes interesadas de la empresa optan por invertir en más administración.

### <a name="composite-sla-impact"></a>Efecto del Acuerdo de Nivel de Servicio compuesto

El _efecto del Acuerdo de Nivel de Servicio compuesto_ (_Commitment level impact_ [Efecto del nivel de compromiso] en el libro) proporciona el efecto fiscal actualizado en función de los cambios en el Acuerdo de Nivel de Servicio sobre el tiempo de actividad. Este cálculo le permite comparar el efecto financiero previsto de ambas opciones. Para calcular este efecto previsto sin la hoja de cálculo, aplique la siguiente fórmula:

> _Efecto del Acuerdo de Nivel de Servicio compuesto = interrupción estimada x tiempo/valor del efecto_

El valor representa las posibles pérdidas que se deben evitar con el cambio en el nivel de compromiso y el nuevo Acuerdo de Nivel de Servicio compuesto.

### <a name="comparison-basis"></a>Base de comparación

La _base de comparación_ evalúa el efecto estándar y el efecto del Acuerdo de Nivel de Servicio compuesto para determinar cuál es el más adecuado en la columna de rendimiento.

### <a name="return-on-loss-avoidance"></a>Rendimiento con la prevención de pérdidas

Si el costo de administrar una carga de trabajo supera las pérdidas potenciales, la inversión propuesta en la administración de la nube podría no ser adecuada. Para comparar el _rendimiento con la prevención de pérdidas_, consulte la columna denominada _Annual ROI****_ (ROI anual). Para calcular esta columna por su cuenta, use esta fórmula:

> _Rendimiento con la prevención de pérdidas = (base de comparación - [costo mensual x 12] / [costo mensual x 12])_

A menos que haya otros factores de costo indirecto que considerar, esta comparación puede sugerir rápidamente si debe haber una mayor inversión en las operaciones en la nube, la resistencia, la confiabilidad u otras áreas.

## <a name="validate-the-commitment"></a>Validación del compromiso

Ya en este punto del proceso se han realizado compromisos: responsabilidad centralizada o delegada, inquilino de Azure y nivel de compromiso. Es necesario validar y documentar cada compromiso para garantizar la alineación del equipo de operaciones en la nube, del equipo de estrategia en la nube y de las partes interesadas de la empresa respecto a este compromiso con el fin de administrar la carga de trabajo.

## <a name="next-steps"></a>Pasos siguientes

Una vez realizados los compromisos, los equipos de operaciones responsables pueden comenzar a configurar la carga de trabajo en cuestión. Para empezar, evalúe varios enfoques para [el inventario y la visibilidad](./inventory.md).

> [!div class="nextstepaction"]
> [Opciones de inventario y visibilidad](./inventory.md)
