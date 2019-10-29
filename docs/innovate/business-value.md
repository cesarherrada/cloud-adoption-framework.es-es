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
ms.openlocfilehash: 643da95396a4983c2642fabcf21340264d0cd1c9
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683335"
---
# <a name="building-consensus-on-the-business-value-of-innovation"></a>Creación de consenso sobre el valor empresarial de la innovación

El primer paso para desarrollar cualquier innovación nueva es identificar la forma en que impulsará el valor empresarial. En este ejercicio se formulan una serie de preguntas que resaltan la importancia de invertir más tiempo en definir el valor empresarial.

## <a name="qualifying-questions"></a>Preguntas calificadoras

Antes de desarrollar cualquier solución (en la nube o local), valide los criterios de valor empresarial:

1. ¿Qué necesidad definida del cliente se busca satisfacer con esta solución?
2. ¿Qué oportunidades para la empresa creará esta solución?
3. ¿Qué resultados empresariales se lograrán con esta solución?
4. ¿Qué motivación de la empresa se atenderá con esta solución?

Si las respuestas a las cuatro preguntas están bien documentadas, es posible que no necesite el resto de este ejercicio. Afortunadamente, esa documentación se puede probar fácilmente. Para probar la documentación y la alineación general, mantenga una breve reunión con las partes interesadas comprometidas de la empresa y otra diferente con el equipo de desarrollo implicado. En ambas reuniones, formule las cuatro preguntas anteriores y compare los resultados.

> [!NOTE]
> La documentación existente **no se debe** compartir con ninguno de los equipos antes de la reunión. Si existe una verdadera alineación, los miembros de cada grupo deben hacer referencia a (o mejor aún, recitar) las hipótesis orientadoras.

> [!WARNING]
> No facilite la reunión. Se trata de una prueba de alineación, no de un ejercicio de creación de una alineación. Al iniciar la reunión, asegúrese de que los asistentes conozcan que el objetivo es probar la alineación direccional con los acuerdos existentes dentro del equipo. Establezca solo un límite de tiempo. Asigne hasta cinco minutos por pregunta y establezca un temporizador para cada una. Cierre la pregunta en cinco minutos, incluso si no se acuerda la respuesta.

Si las respuestas están alineadas direccionalmente, pero representan distintos idiomas e intereses de cada grupo, considere el ejercicio como una victoria. Está listo para continuar con el desarrollo de la solución.

Si una o dos de las respuestas están alineadas direccionalmente, reconozca que el trabajo duro compensa. Ya se ha alineado mejor que la mayoría de las organizaciones. Es muy probable que se produzca un éxito futuro, con una pequeña inversión continua en la alineación. Revise en cada una de las siguientes secciones las ideas que pueden ayudarle a crear más alineación.

Si alguno de los equipos no responde a las cuatro preguntas en treinta minutos, es probable que la alineación y los siguientes esfuerzos tengan un gran impacto sobre este esfuerzo y otros. Preste especial atención a cada una de las siguientes secciones.

## <a name="address-the-big-picture-first"></a>Observe primero la perspectiva general

El marco de adopción de la nube sigue una ruta prescrita a través de la estrategia, plan, preparación y adopción. La innovación en la nube se ajusta a la fase de adopción de este proceso. Cuando las respuestas a las preguntas 3 y 4 anteriores (resultados y motivaciones) no están alineadas, indica que faltó algo en la fase de estrategia del ciclo de vida de la adopción de la nube. Es probable que se produzcan algunos de los escenarios siguientes.

- **Oportunidad de alineación:** Cuando las partes interesadas de la empresa no pueden acordar las motivaciones y los resultados empresariales relacionados con un esfuerzo de innovación en la nube, es síntoma de un desafío mayor. Los ejercicios de la [fase de estrategia en la nube](../strategy/index.md) pueden ser útiles para desarrollar la alineación entre las partes interesadas de la empresa. Además, se recomienda encarecidamente que las mismas partes interesadas formen un [equipo de estrategia en la nube](../organize/cloud-strategy.md) que se reúna con regularidad.

- **Oportunidad de comunicación:** Cuando el equipo de desarrollo no puede acordar las motivaciones y los resultados empresariales, puede ser un síntoma de brechas en la comunicación estratégica. Revisar la estrategia en la nube con el equipo de adopción de la nube puede resolver rápidamente este elemento bloqueador. Varias semanas después de la revisión, el equipo debe repetir el ejercicio de preguntas calificadoras.

- **Oportunidad de priorización:** Una estrategia en la nube es esencialmente una hipótesis de nivel ejecutivo. Las mejores estrategias en la nube están abiertas a la iteración y los comentarios. Si ambos equipos entienden la estrategia, pero todavía no pueden alinear las respuestas a estas preguntas, es posible que las prioridades no estén alineadas. Una sesión con el equipo de adopción de la nube y el equipo de estrategia en la nube podría ayudar a los esfuerzos de ambos grupos. Durante esta sesión, el equipo de adopción de la nube comparte sus respuestas alineadas con las preguntas de perspectiva general. A partir de ahí, una conversación entre el equipo de adopción de la nube y el equipo de estrategia en la nube puede resaltar oportunidades para alinear mejor las prioridades.

Estas grandes oportunidades de perspectiva general suelen revelar maneras de alinear mejor esta solución con la estrategia en la nube. Este ejercicio tiene dos resultados comunes:

- Estas conversaciones pueden dar lugar a mejoras en la estrategia en la nube y una mejor representación de esta importante necesidad del cliente. Este cambio puede dar lugar a un mayor soporte ejecutivo para el equipo.
- Por el contrario, esta conversación podría mostrar que la inversión en otra solución es más adecuada para el equipo de adopción de la nube. En este caso, considere la posibilidad de migrar esta solución antes de continuar con la inversión en innovación. Como alternativa, puede indicar que se necesita un enfoque de desarrollador cívico para probar primero el valor empresarial. En cualquier caso, ayudará al equipo a evitar realizar una gran inversión con retorno empresarial limitado.

## <a name="address-solution-alignment"></a>Solucionar la alineación de la solución

Es bastante habitual que las respuestas a las preguntas 1 y 2 (la necesidad del cliente y la oportunidad de negocio) no se alineen correctamente. Esto es especialmente frecuente durante las primeras fases de ideación y desarrollo. Buscar un equilibrio entre demasiada y poca definición es desafiante para muchos equipos de desarrollo. En el marco de adopción de la nube, se sugieren enfoques eficaces como los bucles de comentarios crear-medir-aprender como la mejor manera de responder a estas preguntas. En la lista siguiente se muestran las oportunidades y los enfoques para crear la alineación.

- **Oportunidad de hipótesis:** Es habitual que varias partes interesadas y equipos de desarrollo tengan demasiadas expectativas para una solución. Cuando ocurre esto, es un signo de que la hipótesis es demasiado imprecisa. Siga las instrucciones que se indican en [crear con la empatía de los clientes](./considerations/build.md) para construir una hipótesis más clara.
- **Oportunidad de creación:** Cuando los equipos están mal alineados porque no están de acuerdo en la forma de resolver la necesidad del cliente, normalmente indica que el equipo se está [retrasando debido a un pico técnico prematuro](./considerations/build.md#reduce-complexity-and-delay-technical-spikes). Para que el equipo se centre en el cliente, inicie la primera iteración y cree un MVP pequeño para abordar parte de la hipótesis. Para obtener más instrucciones que ayuden al equipo a avanzar, consulte [Developing digital inventions](./considerations/invention.md) (Desarrollo de invenciones digitales).
- **Oportunidad de aprendizaje:** Cuando alguno de los equipos está desalineado porque se necesitan requisitos técnicos profundos y requisitos funcionales extensivos, se revela una oportunidad de aprendizaje en metodologías ágiles. Cuando la referencia cultural del equipo no está lista para los procesos ágiles, puede resultar difícil innovar y seguir el ritmo del mercado. Para obtener información sobre los recursos de aprendizaje sobre DevOps y las prácticas ágiles, consulte:
  - [Logre que sus prácticas de DevOps evolucionen](https://docs.microsoft.com/learn/paths/evolve-your-devops-practices)
  - [Creación de aplicaciones con Azure DevOps](https://docs.microsoft.com/learn/paths/build-applications-with-azure-devops)
  - [Implementación de aplicaciones con Azure DevOps](https://docs.microsoft.com/learn/paths/deploy-applications-with-azure-devops/)

El uso de esta metodología y las herramientas de administración del trabajo pendiente en cada sección de la lista anterior puede ayudar a crear la alineación de la solución.

## <a name="next-steps"></a>Pasos siguientes

Una vez que la propuesta de valor empresarial está bien alineada y comunicada, es el momento de empezar a compilar la solución. Vuelva a los [ejercicios de innovación](./index.md) para obtener instrucciones sobre los pasos siguientes.

> [!div class="nextstepaction"]
> [Volver a los ejercicios de innovación para los pasos siguientes](./index.md)
