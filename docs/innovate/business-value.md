---
title: Crear consenso sobre el valor empresarial de la innovación en la nube
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a crear consenso sobre el valor empresarial de la innovación en la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: c57152b92826539a236227636ee115c19bd70e7a
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73565749"
---
# <a name="build-consensus-on-the-business-value-of-innovation"></a>Creación de consenso sobre el valor empresarial de la innovación

El primer paso para desarrollar cualquier innovación nueva es identificar la forma en que puede impulsar el valor empresarial. En este ejercicio, debe responder a una serie de preguntas que destacan la importancia de invertir bastante tiempo cuando la organización define el valor empresarial.

## <a name="qualifying-questions"></a>Preguntas calificadoras

Antes de desarrollar cualquier solución (en la nube o local), responda a las preguntas siguientes para validar los criterios de valor empresarial:

1. ¿Qué necesidad definida del cliente busca satisfacer con esta solución?
1. ¿Qué oportunidades creará esta solución para la empresa?
1. ¿Qué resultados empresariales se lograrán con esta solución?
1. ¿Qué motivación de la empresa se atenderá con esta solución?

Si las respuestas a las cuatro preguntas están bien documentadas, es posible que no necesite realizar el resto de este ejercicio. Afortunadamente, puede probar cualquier documentación fácilmente. Configure dos reuniones breves para probar la documentación y la alineación interna de su organización. Invite a las partes interesadas del negocio confirmadas a una reunión y configure una reunión aparte con el equipo de desarrollo comprometido. Formule las cuatro preguntas anteriores a cada uno de los grupos y compare los resultados.

> [!NOTE]
> La documentación existente **no se debe** compartir con ninguno de los equipos antes de la reunión. Si existe una verdadera alineación, los miembros de cada grupo deben mencionar (o mejor aún, recitar) las hipótesis orientadoras.

<!-- -->

> [!WARNING]
> No facilite la reunión. Esta prueba está destinada a determinar la alineación; no es un ejercicio para crear una alineación. Al iniciar la reunión, recuerde a los asistentes que el objetivo es probar la alineación direccional con los acuerdos existentes dentro del equipo. Establezca un límite de tiempo de cinco minutos para cada pregunta. Establezca un temporizador y cierre cada pregunta transcurridos cinco minutos, aunque los asistentes no hayan acordado una respuesta.

Tenga en cuenta los distintos idiomas e intereses de cada grupo. Si la prueba da como resultado respuestas alineadas direccionalmente, considere que el ejercicio ha sido una victoria. Está listo para pasar al desarrollo de la solución.

Si una o dos de las respuestas están alineadas direccionalmente, reconozca que el trabajo duro compensa. Ya se ha alineado mejor que la mayoría de las organizaciones. Es probable que se produzca un éxito futuro, con una pequeña inversión continua en la alineación. Revise en cada una de las siguientes secciones las ideas que pueden ayudarle a crear más alineación.

Si alguno de los equipos no responde a las cuatro preguntas en 30 minutos, es probable que la alineación y las consideraciones de las siguientes secciones tengan un gran impacto sobre este y otros esfuerzos. Preste especial atención a cada una de las siguientes secciones.

## <a name="address-the-big-picture-first"></a>Observe primero la perspectiva general

Cloud Adoption Framework sigue una ruta prescrita a través de las fases de estrategia, plan, preparación y adopción. La innovación en la nube se ajusta a la fase de adopción de este proceso. Las respuestas a las [preguntas calificadoras](#qualifying-questions) tres y cuatro están relacionadas con los resultados y las motivaciones. Si estas respuestas están mal alineadas, significa que su organización ha omitido algo durante la fase de estrategia del ciclo de vida de adopción de la nube. Es probable que se produzcan algunos de los escenarios siguientes.

- **Oportunidad de alineación:** cuando las partes interesadas de la empresa no pueden acordar las motivaciones y los resultados empresariales relacionados con un esfuerzo de innovación en la nube, es síntoma de un desafío mayor. Los ejercicios de la [fase de estrategia en la nube](../strategy/index.md) pueden ser útiles para desarrollar la alineación entre las partes interesadas de la empresa. Además, se recomienda encarecidamente que las mismas partes interesadas formen un [equipo de estrategia en la nube](../organize/cloud-strategy.md) que se reúna con regularidad.

- **Oportunidad de comunicación:** Cuando el equipo de desarrollo no puede acordar las motivaciones y los resultados empresariales, puede ser un síntoma de brechas en la comunicación estratégica. Para resolver rápidamente este problema, puede revisar la estrategia en la nube con el equipo de adopción de la nube. Varias semanas después de la revisión, el equipo debe repetir el ejercicio de preguntas calificadoras.

- **Oportunidad de priorización:** Una estrategia en la nube es esencialmente una hipótesis de nivel ejecutivo. Las mejores estrategias en la nube están abiertas a la iteración y los comentarios. Si ambos equipos entienden la estrategia, pero todavía no pueden alinear las respuestas a estas preguntas, es posible que las prioridades no estén alineadas. Organice una sesión con el equipo de adopción de la nube y el equipo de estrategia en la nube. Esta sesión puede ser útil para el trabajo de ambos grupos. El equipo de adopción de la nube comienza compartiendo sus respuestas alineadas con las preguntas calificadoras. A partir de ahí, una conversación entre el equipo de adopción de la nube y el equipo de estrategia en la nube puede resaltar oportunidades para alinear mejor las prioridades.

Estas oportunidades generales suelen revelar maneras de alinear mejor la solución innovadora con la estrategia en la nube. Este ejercicio tiene dos resultados comunes:

- Estas conversaciones pueden ayudar a su equipo a mejorar la estrategia en la nube de la organización y a representar mejor las necesidades importantes del cliente. Este cambio puede dar lugar a un mayor soporte ejecutivo para el equipo.
- Por el contrario, estas conversaciones pueden indicar que el equipo de adopción de la nube debe invertir en una solución diferente. En este caso, considere la posibilidad de migrar esta solución antes de continuar con la inversión en innovación. Como alternativa, estas conversaciones pueden indicar que adopta un enfoque de desarrollador cívico para probar primero el valor empresarial. En cualquier caso, ayudarán al equipo a evitar una gran inversión con un retorno empresarial limitado.

## <a name="address-solution-alignment"></a>Solucionar la alineación de la solución

Es bastante habitual que las respuestas a las preguntas uno y dos estén mal alineadas. Durante las primeras fases de concepción y desarrollo, la necesidad de los clientes y la oportunidad de negocio a menudo no se alinean. Muchos equipos de desarrollo perciben como un reto conseguir un equilibrio entre demasiada y poca definición. Cloud Adoption Framework recomienda enfoques eficaces como los bucles de comentarios crear-medir-aprender para responder a estas preguntas. En la lista siguiente se muestran las oportunidades y los enfoques para crear la alineación.

- **Oportunidad de hipótesis:** Es habitual que varias partes interesadas y equipos de desarrollo tengan demasiadas expectativas para una solución. Las expectativas irreales pueden ser un signo de que la hipótesis es demasiado imprecisa. Siga las instrucciones que se indican en [Creación con la empatía de los clientes](./considerations/build.md) para construir una hipótesis más clara.
- **Oportunidad de creación:** es posible que los equipos no estén alineados porque no están de acuerdo en la forma de resolver las necesidades del cliente. Este desacuerdo suele indicar que el equipo está [retrasado por un pico técnico prematuro](./considerations/build.md#reduce-complexity-and-delay-technical-spikes). Para que el equipo se centre en el cliente, inicie la primera iteración y cree un producto mínimo viable (MVP) pequeño para abordar parte de la hipótesis. Para obtener más instrucciones que ayuden al equipo a avanzar, consulte [Desarrollo de invenciones digitales](./considerations/invention.md).
- **Oportunidad de aprendizaje:** cualquier equipo puede estar mal alineado porque necesita requisitos técnicos profundos y requisitos funcionales amplios. Esta necesidad puede conducir a una oportunidad de entrenamiento en metodologías ágiles. Cuando la referencia cultural del equipo no está lista para los procesos ágiles, puede resultar difícil innovar y seguir el ritmo del mercado.  Para obtener información sobre los recursos de aprendizaje sobre DevOps y las prácticas ágiles, consulte:
  - [Logre que sus prácticas de DevOps evolucionen](https://docs.microsoft.com/learn/paths/evolve-your-devops-practices)
  - [Creación de aplicaciones con Azure DevOps](https://docs.microsoft.com/learn/paths/build-applications-with-azure-devops)
  - [Implementación de aplicaciones con Azure DevOps](https://docs.microsoft.com/learn/paths/deploy-applications-with-azure-devops)

El seguimiento de la metodología y las herramientas de administración del trabajo pendiente de cada sección de este artículo puede ayudarle a crear la alineación de la solución.

## <a name="next-steps"></a>Pasos siguientes

Cuando la propuesta de valor empresarial está bien alineada y comunicada, está a punto para empezar a compilar la solución.
> [!div class="nextstepaction"]
> [Volver a los ejercicios de innovación para los pasos siguientes](./index.md)
