---
title: Introducción al modelo de funcionamiento
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Descripción del modelo de funcionamiento de Cloud Adoption Framework.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/07/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: overview
ms.custom: operating-model
ms.openlocfilehash: 85123239ad6dd4a389a2b32692638a3debe98951
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72556639"
---
# <a name="establish-an-operating-model-for-the-cloud"></a>Establecimiento de un modelo de funcionamiento para la nube

La adopción de la nube es un esfuerzo iterativo que se centra en las actividades que realiza en la nube. La estrategia de la nube describe la transformación digital necesaria para guiar los programas empresariales a medida que los diversos equipos ejecutan los proyectos de adopción. La planeación y preparación ayudan a garantizar el éxito de cada uno de esos elementos importantes. Todos los pasos de adopción de la nube se concretan en proyectos tangibles con objetivos, plazos y presupuestos administrables.

Se puede realizar con relativa facilidad el seguimiento y medición de los esfuerzos de adopción, incluso cuando implican varias iteraciones y versiones proyectadas. Cada fase del ciclo de vida de adopción es importante. Cada fase es propensa a experimentar posibles obstáculos debido a restricciones empresariales, culturales y tecnológicas. Pero cada fase depende en gran medida del modelo operativo subyacente.

**Si la adopción describe lo que está haciendo, el modelo operativo define quién está detrás de la adopción y cómo este la habilita.**

Satya Nadella dijo **"La cultura se come la estrategia para desayunar"** . El modelo operativo es la encarnación de la cultura de TI, capturada en varios procesos medibles. Cuando la nube está basada en un sólido modelo operativo, la referencia cultural conducirá a la estrategia, lo que acelerará la adopción y los valores empresariales. Por el contrario, si la adopción es correcta, pero no hay ningún modelo operativo, los beneficios que se obtienen a cambio pueden ser impresionantes pero de muy corta duración. Para conseguir un éxito a largo plazo, es fundamental que la adopción y los modelos operativos avancen en paralelo.

## <a name="establish-your-operating-model"></a>Establecimiento del modelo de funcionamiento

Los modelos de funcionamiento actuales pueden escalarse para respaldar el proceso de adopción de la nube. Un modelo operativo moderno puede ayudarle a eliminar los bloqueos no técnicos en la adopción de la nube.

Esta sección de Cloud Adoption Framework ofrece un modelo de funcionamiento viable que proporciona orientación sobre las decisiones no técnicas. Este modelo de funcionamiento consta de tres metodologías que pueden ayudar en la creación de su propio modelo de funcionamiento en la nube:

- [Control](../govern/index.md): Garantiza la coherencia entre los esfuerzos de adopción. Se adapta a los requisitos de gobernanza o cumplimiento para mantener un entorno entre nubes bien administrado.
- [Administración](../manage/index.md): Adapta los procesos en curso para la administración operativa de la tecnología para maximizar la obtención de valor y la reducción al mínimo de las interrupciones.
- [Organizar](../organize/index.md): A medida que el modelo operativo se consolida, también lo hace la organización de los diversos equipos y funcionalidades que respaldan el modelo operativo.

## <a name="aligning-operating-models"></a>Alineación de los modelos operativos

La nube y la economía digital han sacado a la luz la necesidad de varios modelos operativos. A veces, esta necesidad viene originada por un requisito que obliga a admitir varias nubes públicas. Con frecuencia, esta necesidad destaca especialmente durante la transición desde un entorno local a la nube. En todos los escenarios, es importante alinear los modelos operativos para obtener el máximo rendimiento y la mínima redundancia.

Los analistas predicen un gran aumento en la adopción de varias nubes. Muchos clientes ya están actuando en esa dirección. Lamentablemente, los clientes informan de que se encuentran con desafíos importantes a la hora de trabajar con varias nubes. La duplicación de recursos, procesos, aptitudes y tecnologías da como resultado un aumento de los costos y no el ahorro que prometían las predicciones sobre el uso de la nube. Para evitar esta tendencia, se recomienda a los clientes adoptar un modelo operativo especializado. Al alinear los modelos operativos, siempre debería haber un **modelo operativo general**. Los **modelos operativos especializados** adicionales se deberían aprovechar en escenarios específicos que admitan desviaciones del modelo estándar.

- **Modelo operativo general:** El modelo operativo general se alinea con una única plataforma de nube pública o privada. Las operaciones de esa plataforma definen los estándares, directivas y procesos operativos. Este modelo operativo debe ser el medio principal para potenciar la estrategia de avance de la nube. En este modelo, el objetivo es sacar el máximo partido al principal proveedor de nube durante la mayor parte del proceso de adopción.

- **Modelo operativo especializado:** Puede que un proveedor de nube alternativo sea la mejor opción para lograr unos resultados empresariales concretos. Cuando hay un caso empresarial importante, los estándares, las directivas y los procesos del modelo operativo general se aplican al nuevo proveedor de nube, pero después se modifican para ajustarse al caso de uso concreto.

Si Azure es la plataforma principal elegida, las guías y los procedimientos recomendados de cada una de las secciones del modelo operativo enumeradas anteriormente resultarán valiosos en la creación de su modelo operativo. Pero este marco es consciente de que no todos nuestros lectores se han decantado por Azure como plataforma principal. Para dar cabida a este público más amplio, el contenido teórico de cada sección se puede aplicar a modelos operativos de nubes públicas o privadas con resultados similares.

## <a name="next-steps"></a>Pasos siguientes

La gobernanza es un primer paso habitual en el establecimiento de un modelo de funcionamiento para la nube.

> [!div class="nextstepaction"]
> [Más información sobre la gobernanza de la nube](../govern/index.md)
