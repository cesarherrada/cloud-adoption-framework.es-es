---
title: 'Importancia crítica para la empresa: administración y operaciones de la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Importancia crítica para la empresa: administración y operaciones de la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 7e7618163b15d17eab51571779e573dd9acb726e
ms.sourcegitcommit: 73dbedf580951f25bf4b5544b83451cb075b1fa1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "72805820"
---
# <a name="business-commitment-in-cloud-management"></a>Compromiso empresarial en la administración de la nube

La definición de un compromiso empresarial es un ejercicio de equilibrar prioridades. El objetivo es alinear el nivel adecuado de administración operativa con un costo operativo aceptable. La búsqueda de ese equilibrio requiere algunos puntos de datos y cálculos, que se describen en las secciones siguientes.

![Equilibrio entre costos y resistencia](../../_images/manage/business-commitment-scale.png)

Los compromisos de estabilidad empresarial (a través de la resistencia técnica u otros efectos del Acuerdo de Nivel de Servicio) son una decisión de justificación empresarial. Para la mayoría de las cargas de trabajo de un entorno, es suficiente un nivel de base de referencia de administración de la nube. Para otros, un aumento de los costos de 2&ndash;4x se justifica fácilmente por el posible efecto de las interrupciones en el negocio. Los artículos anteriores de esta serie ayudan a comprender la clasificación y el efecto de las interrupciones en varias cargas de trabajo. Este artículo le ayudará a calcular el rendimiento. Como se describe en la siguiente imagen, en cada nivel de administración de la nube hay puntos de inflexión en los que los costos pueden aumentar más rápido que la resistencia. Esos puntos de inflexión requerirán decisiones y compromisos empresariales detallados.

## <a name="determining-a-proper-commitment-with-the-business"></a>Determinación de un compromiso adecuado con el negocio

Para cada carga de trabajo de la cartera, el equipo de operaciones en la nube y el equipo de estrategia en la nube deben alinearse en el nivel de administración que proporciona directamente el equipo de operaciones en la nube.

Los siguientes son aspectos clave que se deben alinear al establecer un compromiso con el negocio:

- Requisitos previos de las operaciones de TI
- Responsabilidad de administración
- Inquilino en la nube
- Factores de costo indirecto
- ROI con la prevención de pérdidas
- Validación del nivel de administración

En el resto de este artículo se describe cada uno de estos criterios como ayuda para tomar una decisión.

## <a name="it-operations-prerequisites"></a>Requisitos previos de las operaciones de TI

En la [Guía de administración de Azure](../azure-management-guide/index.md) se describen las herramientas de administración disponibles en Azure. Antes de llegar a un compromiso con la empresa, el departamento de TI debe determinar una base de referencia de administración estándar que se aplique a todas las cargas de trabajo administradas. Después, debe calcular los costos de administración estándares para cada una de las cargas de trabajo administradas en la cartera de TI en función de la cantidad de núcleos de CPU, del espacio en disco y de otras variables relacionadas con los recursos. También estimará un Acuerdo de Nivel de Servicio compuesto para cada carga de trabajo en función de la arquitectura.

> [!TIP]
> Los equipos de operaciones de TI a menudo usan un tiempo de actividad mínimo del 99,9 % para el Acuerdo de Nivel de Servicio compuesto inicial. También pueden optar por normalizar los costos de administración en función de la carga de trabajo media, especialmente en el caso de las soluciones con requisitos mínimos de registro y almacenamiento. Calcular el promedio de los costos de algunas cargas de trabajo de importancia intermedia puede ser un buen punto de partida para las conversaciones iniciales.

> [!TIP]
> Para los lectores que usen el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube, los campos de administración de las operaciones deben actualizarse para que reflejen estos requisitos previos. Esos campos incluyen el nivel de compromiso, el Acuerdo de Nivel de Servicio compuesto y el costo mensual. El costo mensual debe representar el costo mensual agregado de las herramientas de administración de las operaciones.

La base de la administración de las operaciones servirá como punto de partida que validar en las siguientes secciones.

## <a name="management-responsibility"></a>Responsabilidad de administración

En un entorno local tradicional, los costos de administración del entorno se suelen presuponer como costos ocultos de las operaciones de TI. En la nube, la administración es una decisión intencionada con impacto presupuestario directo. Los costos de cada función de administración se pueden atribuir más directamente a cada carga de trabajo implementada en la nube. Este enfoque permite mayor control, pero exige a los equipos de operaciones en la nube y los equipos de estrategia en la nube que celebren primero en un acuerdo sobre las responsabilidades.

Las organizaciones también pueden optar por [externalizar algunas de sus funciones de administración actuales a algún proveedor de servicios](https://www.microsoft.com/cloud-adoption-framework-offers?ot=manage). Estos proveedores de servicios pueden usar [Azure Lighthouse](https://azure.com/lighthouse) para ofrecer a las organizaciones más precisión y control al conceder acceso a los recursos, además de mayor transparencia en las acciones que realizan.

**Responsabilidad delegada**: dado que no es necesario centralizar y adoptar una sobrecarga de administración operativa, se están pensando nuevos enfoques para las operaciones de TI de muchas organizaciones. Un enfoque típico es la responsabilidad delegada. En un modelo de excelencia en la nube, las operaciones y la automatización de la plataforma proporcionan herramientas de administración autoservicio que pueden aprovechar los equipos de operaciones empresariales, independientemente de los equipos de operaciones de TI centrales. Este enfoque proporciona a las partes interesadas de la empresa un control total sobre los presupuestos relacionados con la administración. También permite a al centro de excelencia de la nube (CCoE) asegurarse de que se implementa correctamente un mínimo de barreras. En este modelo, el equipo de TI actúa como agente y guía que ayuda a la empresa a tomar decisiones sensatas. Las operaciones empresariales supervisan las operaciones cotidianas de las cargas de trabajo dependientes.

**Responsabilidad centralizada**: los requisitos de cumplimiento, la complejidad técnica y algunos modelos de servicios compartidos pueden requerir un modelo de TI central. En este modelo, el equipo de TI aún tiene las responsabilidades de administración de las operaciones. Por tanto, el diseño del entorno, los controles de administración y las herramientas de gobernanza se pueden administrar y controlar centralmente, lo que restringe el rol de las partes interesadas de la empresa al realizar compromisos de administración. Sin embargo, los costos y la visibilidad de la arquitectura de los enfoques en la nube facilitan mucho a los equipos de TI centralizados la comunicación de los costos y el nivel de administración de cada carga de trabajo.

**Modelo mixto:** la clasificación es la esencia de los modelos mixtos en cuanto a las responsabilidades de administración. Las empresas que se encuentran en medio de una transformación de sus instalaciones locales a la nube pueden necesitar un modelo operativo local primero durante un tiempo. Otras empresas con requisitos estrictos de cumplimiento o que dependan de contratos a largo plazo con proveedores externos de TI pueden necesitar un modelo operativo centralizado. A pesar de estos tipos de restricciones, las empresas necesitan innovar. En los escenarios de rápida innovación, en medio de un modelo de responsabilidad centralizada en un equipo de TI central, la clasificación y un modelo mixto pueden proporcionar equilibrio. En este enfoque, un equipo de TI central proporciona un modelo operativo centralizado para todas las cargas de trabajo críticas o que contengan información confidencial. Sin embargo, el resto de clasificaciones de las cargas de trabajo se pueden colocar en un entorno de nube diseñado para responsabilidades delegadas. El enfoque de responsabilidad centralizada actúa como modelo operativo general. La empresa tiene flexibilidad para aprovechar un modelo operativo especializado, con el soporte y la confidencialidad necesarios.

El primer paso consiste en confirmar un enfoque de responsabilidad que dé forma a los siguientes compromisos.

**¿Qué organización será responsable de la administración de las operaciones diarias de esta carga de trabajo?**

## <a name="cloud-tenancy"></a>Inquilino en la nube

Para la mayoría de las empresas, la administración es más fácil cuando todos los recursos residen en un único inquilino. Sin embargo, algunas organizaciones necesitarían mantener varios inquilinos. En el artículo sobre la [centralización de las operaciones de administración con Azure Lighthouse](../centralize-operations.md) se proporcionan algunos ejemplos en los que las empresas pueden requerir entornos de Azure de varios inquilinos.

**¿Residirá esta carga de trabajo en un único inquilino de Azure junto con todas las demás?**

## <a name="soft-cost-factors"></a>Factores de costo indirecto

En la siguiente sección de este artículo se describe un enfoque comparativo del rendimiento en relación con los procesos y las herramientas de administración. Al final de esta sección cada carga de trabajo analizada medirá los costos de administración en relación con el impacto previsto de las interrupciones en la empresa. Este enfoque proporcionará una forma relativamente sencilla de comprender si se justifica la inversión en enfoques de administración más completos.

Antes de calcular los números, es importante examinar los factores de costo indirecto. Los factores de costo indirecto producen un rendimiento difícil de medir mediante ahorro en los costos fijos, que sería visible en un balance de resultados. Los factores de costo indirecto son importantes, ya que pueden indicar una necesidad de invertir en más administración que la que sería prudente desde el punto de vista fiscal.

Estos son algunos ejemplos de los factores que mencionamos:

- Uso diario de una carga de trabajo por parte del Consejo o el consejero delegado.
- Uso de una carga de trabajo por parte del _x %_ de clientes que conduce a un mayor impacto en los ingresos por otra parte.
- Efecto sobre la satisfacción de los empleados.

El siguiente punto de datos necesario para realizar un compromiso es una lista de los factores de costo indirecto. No es necesario documentarlas en esta fase, pero la parte interesada de la empresa debe ser consciente de la importancia de estos factores y su exclusión de los siguientes cálculos.

## <a name="calculate-loss-avoidance-roi"></a>Cálculo de la ROI con la prevención de pérdidas

Al calcular el rendimiento relativo en los costos de administración de las operaciones, el equipo de TI responsable de las operaciones en la nube debe cumplir los requisitos previos anteriores y presuponer un nivel mínimo de administración para todas las cargas de trabajo.

El siguiente compromiso que debe realizarse es una aceptación por parte de la empresa de los costos asociados con la oferta administrada según la base de referencia.

**¿Acuerda la empresa invertir en la oferta de base de referencia para cumplir los estándares mínimos de las operaciones en la nube?**

Si la empresa no está de acuerdo con ese nivel de administración, debe idearse una solución que la permita continuar sin que ello afecte de forma significativa a las operaciones en la nube de otras cargas de trabajo.

Si la empresa desea un nivel superior, el resto de esta sección le ayudará a validar esa inversión y el rendimiento asociado (en forma de prevención de pérdidas).

### <a name="increased-levels-of-management-design-principles-and-service-catalog"></a>Mayores niveles de administración: principios de diseño y catálogo de servicios

En el caso de las soluciones administradas, existen varios principios de diseño y soluciones de plantilla que se pueden aplicar además de la base de referencia de administración. Todos los principios de diseño para la confiabilidad y la resistencia suman costos operativos a la carga de trabajo. Para que el equipo de TI y la empresa acuerden estos compromisos adicionales, es importante comprender las posibles pérdidas que se pueden evitar con esa mayor inversión.

Los cálculos siguientes le guiarán por las fórmulas para comprender mejor la comparación entre las pérdidas y el aumento de las inversiones en administración. Para instrucciones sobre cómo calcular el costo de la mayor administración, consulte los artículos sobre la [automatización de la carga de trabajo](./workload.md) y la [automatización de la plataforma](./platform.md).

> [!TIP]
> Para los lectores que usen el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube, los campos de administración de las operaciones deben actualizarse para que reflejen cada conversación. Esos campos incluyen el nivel de compromiso, el Acuerdo de Nivel de Servicio compuesto y el costo mensual. El costo mensual debe representar el costo mensual agregado de las herramientas de administración de las operaciones. Una vez actualizados, esos campos actualizarán las fórmulas de ROI y los campos siguientes.

### <a name="estimate-outage-hours-per-year"></a>Estimación de las interrupciones (horas al año)

El "Acuerdo de Nivel de Servicio compuesto" es el Acuerdo de Nivel de Servicio basado en la implementación de cada recurso en la carga de trabajo. Ese campo controlará la "interrupción estimada" (Est. Outage*** [Interrupción estimada] en el libro). Para calcular la interrupción estimada en horas al año sin usar el libro, aplique la siguiente fórmula:

**Interrupción estimada = (1 - porcentaje del Acuerdo de Nivel de Servicio compuesto) /* número de horas de un año**

En el libro se usa el valor predeterminado de 8760 horas al año.

### <a name="standard-loss-impact"></a>Efecto estándar de las pérdidas

El efecto estándar de las pérdidas ("Standard impact" [Efecto estándar] en el libro) pronostica el efecto financiero de las interrupciones, suponiendo que la predicción "interrupción estimada" resulte precisa. Para calcular esta previsión sin usar el libro, aplique la siguiente fórmula:

**Efecto estándar = interrupción estimada @ tres novenos del tiempo de actividad /* tiempo/valor del efecto**

Esto sirve como base de referencia del costo si las partes interesadas de la empresa optan por invertir en más administración.

### <a name="composite-sla-impact"></a>Efecto del Acuerdo de Nivel de Servicio compuesto

El efecto del Acuerdo de Nivel de Servicio compuesto ("Commitment level impact" [Efecto del nivel de compromiso] en el libro) proporciona el efecto fiscal actualizado en función de los cambios en el Acuerdo de Nivel de Servicio sobre el tiempo de actividad. Esto le permite comparar el efecto financiero previsto de ambas opciones. Para calcular este efecto previsto sin la hoja de cálculo, aplique la siguiente fórmula.

**Efecto del Acuerdo de Nivel de Servicio compuesto = interrupción estimada /* tiempo/valor del efecto**

El valor representa las posibles pérdidas que se deben evitar con el cambio en el nivel de compromiso y el nuevo Acuerdo de Nivel de Servicio compuesto.

### <a name="comparison-basis"></a>Base de comparación

La base de comparación evalúa el efecto estándar y el efecto del Acuerdo de Nivel de Servicio compuesto para determinar cuál es el más adecuado en la columna de rendimiento.

### <a name="return-on-loss-avoidance"></a>Rendimiento con la prevención de pérdidas

Si el costo de administrar una carga de trabajo supera las pérdidas potenciales, la inversión propuesta en la administración de la nube podría no ser adecuada. Para comparar el "rendimiento con la prevención de pérdidas", consulte la columna denominada "Annual ROI***" (ROI anual). Para calcular esta columna por su cuenta, use esta fórmula:

**Rendimiento con la prevención de pérdidas = (base de comparación - [costo mensual /* 12]) // [costo mensual /* 12])**

A menos que haya otros factores de costo indirecto que considerar, esta comparación puede sugerir rápidamente si debe haber una mayor inversión en las operaciones en la nube, la resistencia, la confiabilidad u otras áreas.

## <a name="validate-the-commitment"></a>Validación del compromiso

Ya en este punto del proceso se han realizado compromisos: responsabilidad centralizada o delegada, inquilino de Azure y nivel de compromiso.
Es necesario validar y documentar cada compromiso para garantizar la alineación del equipo de operaciones en la nube, del equipo de estrategia en la nube y de las partes interesadas de la empresa respecto a este compromiso con el fin de administrar la carga de trabajo.

## <a name="next-steps"></a>Pasos siguientes

Una vez realizados los compromisos, los equipos de operaciones responsables pueden comenzar la configuración de la carga de trabajo en cuestión. Para empezar, evalúe varios enfoques para [el inventario y la visibilidad](./inventory.md).

> [!div class="nextstepaction"]
> [Opciones de inventario y visibilidad](./inventory.md)
