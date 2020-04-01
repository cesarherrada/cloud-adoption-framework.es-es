---
title: Equilibrio de prioridades en la competencia
description: Descubra estrategias para equilibrar prioridades contrapuestas.
author: BrianBlanchard
ms.author: brblanch
ms.date: 03/04/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: strategy
ms.openlocfilehash: a0524d8e7cd48f3b93191d9633bb57b10fb2261b
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80353697"
---
# <a name="balance-competing-priorities"></a>Equilibrio de prioridades en la competencia

Embarcarse en una experiencia de transformación digital sirve de impulso para las partes interesadas en los equipos empresariales y tecnológicos. El camino hacia el éxito se basa principalmente en la capacidad de la organización para equilibrar prioridades contrapuestas.

Al igual que sucede con otras transformaciones digitales, la adopción de la nube sacará a la luz prioridades contrapuestas a lo largo del ciclo de vida de la adopción. De forma similar a otras formas de transformación, la capacidad de encontrar el equilibrio en esas prioridades tendrá un impacto significativo en la consecución del valor empresarial. Equilibrar estas prioridades contrapuestas requerirá conversaciones francas (y a veces complicadas) entre las partes interesadas (y, en ocasiones, con los colaboradores individuales).

En este artículo se describen algunas de las prioridades contrapuestas que se tratan normalmente durante la ejecución de cada metodología. Esperamos que este conocimiento avanzado le ayude a prepararse mejor para esas conversaciones cuando desarrolle la estrategia de adopción de la nube.

![Introducción al ciclo de vida de adopción de la nube](../_images/caf-overview.png)

Las secciones siguientes están en línea con el gráfico anterior del ciclo de vida de adopción de la nube. Sin embargo, es importante tener en cuenta que la adopción de la nube es iterativa (no es un proceso secuencial). Estas prioridades contrapuestas surgirán (y, a veces, volverán a reaparecer) en varios puntos del recorrido de adopción de la nube.

## <a name="general-theme-of-the-cloud-adoption-framework-approach"></a>Tema general del enfoque de Cloud Adoption Framework

Las soluciones homogéneas y el planeamiento avanzado se basan en una serie de suposiciones que pueden resultar (o no) adecuadas a lo largo del tiempo. La adopción de la nube a menudo es una experiencia novedosa para los equipos técnicos y empresariales. Al igual que sucede con la mayoría de las nuevas experiencias u oportunidades de aprendizaje, hay muchas probabilidades de que esas suposiciones resulten falsas.

Los siguientes principios ágiles de decisiones técnicas diferidas constituyen el enfoque preferido en la mayoría de instrucciones de este marco. Este enfoque sigue un patrón coherente: permite establecer un estado final general, pasar rápidamente a la implementación inicial, probar y validar suposiciones, refactorizar pronto para dar respuesta a las suposiciones. Este tipo de mentalidad de crecimiento maximiza el aprendizaje y minimiza los riesgos para el valor empresarial. Sin embargo, esta mentalidad requiere un cierto grado de aceptación de la ambigüedad.

En ocasiones, la ambigüedad puede ser peor (o más peligrosa) que las suposiciones falsas. Aunque este marco de trabajo se basa en el aprendizaje y en dar respuesta a la ambigüedad durante la ejecución, hay muchas situaciones que requieren que el equipo opte por enfoques basados en análisis o en suposiciones. En las secciones siguientes se intentará ilustrar al menos un "ejemplo de ámbito ampliado" en cada sección para ilustrar aquellas ocasiones en las que una segunda iteración más profunda sería valiosa.

## <a name="balance-during-strategy"></a>Equilibrio durante la estrategia

El objetivo principal de la metodología de estrategia es desarrollar la alineación entre las partes interesadas. Una vez definida, esa posición estratégica alineada controlará los comportamientos en cada una de las metodologías para garantizar que las decisiones técnicas estén alineadas con los resultados de negocio deseados. Promover la alineación entre las partes interesadas crea un conjunto común de prioridades contrapuestas: la **importancia de la justificación** en comparación con el **tiempo para que se produzca el efecto en el negocio**.

**Prioridades contrapuestas:**

- **Importancia de la justificación**: las partes interesadas suelen querer un análisis financiero en profundidad y una justificación comercial completa para que acepten alinearse con una dirección estratégica. Lamentablemente, ese nivel de análisis puede requerir un período prolongado de tiempo que permita la recopilación y el análisis de datos.
- **Tiempo para que se produzca el efecto en el negocio:** por el contrario, las partes interesadas suelen ser responsables de tener que entregar resultados empresariales dentro de los plazos de tiempo definidos. Un análisis y evaluación prolongados pueden poner en riesgo esos resultados antes incluso de que se inicie el trabajo técnico.

**Ámbito mínimo:** la búsqueda de este equilibrio requiere debates entre las partes interesadas al principio del proceso. La metodología de estrategia sugiere limitar el ámbito de la alineación durante este esfuerzo inicial. En el enfoque sugerido, las partes interesadas se centran en alinearse en torno a un conjunto de motivaciones principales, resultados medibles y una justificación comercial de alto nivel. Se recomienda que, a continuación, las partes interesadas realicen rápidamente un pequeño número de proyectos iniciales o pilotos para impulsar las oportunidades de aprendizaje necesarias.

**Ejemplo de ámbito ampliado:** si el análisis empresarial inicial indica un alto riesgo de un efecto negativo en la empresa, es posible que las partes interesadas tengan que detenerse y evaluar con mayor precaución un análisis más profundo durante la justificación comercial.

## <a name="balance-during-plan"></a>Equilibrio durante el planeamiento

Al igual que con las prioridades de estrategia, durante el planeamiento es necesario equilibrar: la profundidad del planeamiento inicial frente a las decisiones técnicas diferidas.

**Prioridades contrapuestas:**

- La **profundidad del planeamiento inicial** con respecto a la implementación técnica en la nube a menudo contiene un gran número de suposiciones. Especialmente cuando el equipo tiene lagunas de aptitudes, el entorno se ve afectado por brechas de detección, o las cargas de trabajo no tienen los estados finales de arquitectura claramente definidos. Todas estas suposiciones son habituales en los planes detallados de adopción de la nube. Para eliminar estas suposiciones, se necesita experimentación, proyectos pilotos y análisis cualitativos.
- En las **decisiones técnicas diferidas** se supone que cuanto más se tarda en tomar una decisión técnica, más precisa es esa decisión. Los siguientes principios de planeamiento de productos ágiles le ayudarán a retrasar las decisiones técnicas, lo cual permitirá que se realicen en el momento adecuado con información suficiente. Sin embargo, este enfoque da como resultado un grado mucho más alto de ambigüedad en el plan inicial.

**Ámbito mínimo:** los enfoques de desarrollo de productos ágiles se recomiendan para impulsar una rápida actuación en los planes administrables. La metodología de planeamiento recomienda los siguientes pasos para lograr este equilibrio. Realice un inventario completo del patrimonio digital mediante herramientas de detección automática, pero utilice la racionalización incremental para planear los próximos 1 a 3 meses de trabajo. Asegúrese de que la alineación adecuada está establecida para avanzar rápidamente. Cree un plan de preparación de aptitudes para el equipo asignado. Aproveche la plantilla del plan de adopción de la nube para implementar rápidamente un trabajo pendiente inicial.

**Ejemplo de ámbito ampliado:** en ocasiones, la entrega de un plan de adopción de la nube puede estar respondiendo a un evento empresarial con límite de tiempo o de gran impacto. Cuando el éxito requiere el traslado de un gran número de recursos en un período de tiempo fijo, los pasos anteriores se suelen seguir con un esfuerzo de planeación más profundo. La clave del éxito en estos escenarios es planear lo suficiente para empezar a trabajar y, a continuación, planear la involucración plena. Este enfoque reduce la probabilidad de que el planeamiento bloquee los resultados empresariales.

## <a name="balance-during-ready"></a>Equilibrio durante la preparación

Cuando los equipos de adopción están preparando los primeros pasos en la nube, a menudo hay prioridades contrapuestas entre el tiempo para la adopción y las operaciones a largo plazo. Puede que el equipo tenga dificultades a la hora de decidir entre estar bien preparado para entregar la tarea en cuestión o estar bien administrado. Este esfuerzo es necesario en los entornos de TI tradicionales, en los que el hecho de desarrollar una plataforma requiere recursos físicos y ciclos de adquisición. Sin embargo, cuando se define toda la plataforma de TI en código, las tácticas de desarrollo tradicionales (como la refactorización) reducen la necesidad de estar bien administrado desde el principio.

**Prioridades contrapuestas:**

- **Operaciones a largo plazo:** a menudo, los clientes se bloquean por el deseo de tener un entorno de nube que cumpla la paridad de características con los sistemas actuales de administración de operaciones, gobernanza y seguridad. En un estudio actual de clientes, más del 90 % de estos necesitaron apoyo para superar esta mentalidad. Este elemento de bloqueo supone meses de retraso lo cual ralentiza o impide el impacto en la empresa.
- **Tiempo para la adopción:** las herramientas basadas en la nube como Azure Policy, Azure Blueprints y los grupos de administración permiten facilitar la refactorización en la plataforma de TI. Además, las zonas de aterrizaje predefinidas proporcionan posiciones bien fundamentadas para acelerar la implementación en un entorno que ya cumple muchos de los requisitos de paridad de características. Gracias a todo esto, existen oportunidades de acelerar el tiempo de comercialización, con un impacto mínimo en las operaciones a largo plazo.

**Ámbito mínimo:** la metodología de preparación describe una ruta directa desde la adopción rápida a las operaciones a largo plazo. Este enfoque comienza con una introducción básica a las herramientas que permiten la refactorización del entorno. En función de esas herramientas y de los requisitos del entorno, se guiará a los clientes a una selección de zonas de aterrizaje predefinidas (cada una de ellas proporcionada mediante modelos de infraestructura como código). Después, ese código puede refactorizarse durante el transcurso de la adopción de la nube para mejorar las operaciones, la seguridad y las posiciones de administración.

**Ejemplo de ámbito ampliado:** en el caso de los equipos en los que el plan de adopción establece un objetivo a medio plazo (menos de 24 meses) para hospedar **más de 1000 recursos (aplicaciones, infraestructura o recursos de datos) en la nube**, se recomienda un enfoque más sólido de las zonas de aterrizaje. En estas situaciones, las metodologías de gobierno y administración se deben tener en cuenta durante las conversaciones iniciales sobre zonas de aterrizaje. Sin embargo, esta consideración más profunda suele agregar semanas o meses a un plan de adopción de la nube. Para minimizar el impacto en los resultados de la empresa, el equipo de adopción debe probar cargas de trabajo reales en la nube en paralelo con la creación de una zona de aterrizaje más consolidada y una solución de arquitectura central.

## <a name="balance-during-migrate"></a>Equilibrio durante la migración

Durante los esfuerzos de migración, es habitual que los equipos de adopción asuman que las cargas de trabajo se rehospedarán en la nube con su configuración actual. Esto se contrapone directamente con un enfoque de previsión con el que rediseñar cada carga de trabajo y aprovechar mejor las capacidades de la nube. No obstante, los dos enfoques no son mutuamente excluyentes y pueden ser complementarios cuando se administran mediante un proceso común.

**Prioridades contrapuestas:**

- **Rehospedaje:** a menudo, los clientes equiparan la migración a un movimiento _lift-and-shift_ de replicación de todos los recursos en la nube en su configuración de estado actual. Esto da lugar a un pequeño desfase en la cartera de TI. Este enfoque también es la manera más rápida de retirar recursos de un centro de datos existente.
- **Rediseño:** la modernización de la arquitectura de cada carga de trabajo maximiza el valor de la nube en relación con el costo, el rendimiento y las operaciones. Sin embargo, este enfoque es mucho más lento y a menudo requiere acceso al código fuente de cada aplicación.

**Ámbito mínimo:** durante el planeamiento de la fase temprana, use la opción de rehospedaje para el planeamiento, teniendo presente que esta opción es una suposición empresarial inicial y no una decisión técnica. En la metodología de migración, el equipo de adopción comprobaría posteriormente esta suposición para cada carga de trabajo migrada. Esta metodología sigue los pasos de evaluación, migración y promoción para cada carga de trabajo, o grupo de estas, con lo que se crea una factoría de migración. Durante la fase de evaluación, el equipo de adopción evalúa la adecuación técnica y la arquitectura de cada carga de trabajo. Ese esfuerzo de evaluación rara vez da como resultado un enfoque puro de lift-and-shift, ya que muchos de los componentes de la arquitectura tienden a seleccionarse para su refactorización y modernización.

**Ejemplo de ámbito ampliado:** en el caso de cargas de trabajo críticas o de alta confidencialidad como, por ejemplo, un sistema central o una aplicación de microservicios de varios niveles, puede que se necesite una evaluación más profunda de la carga de trabajo durante la fase de evaluación. En estas situaciones de rediseño, se recomienda que los clientes utilicen el examen de la arquitectura de Azure y el marco de arquitectura de Azure para refinar los requisitos de las cargas de trabajo durante la evaluación.

## <a name="balance-during-innovate"></a>Equilibrio durante la innovación

Una verdadera innovación orientada hacia el cliente crea prioridades comunes contrapuestas entre la necesidad de ofrecer un conjunto de características planeadas y un proceso de desarrollo de empatía con el cliente.

**Prioridades contrapuestas:**

- Centrado en las características: los planes iniciales de innovación se basan en el patrimonio digital existente y en las funcionalidades de la nube para ofrecer un conjunto de características que satisfagan las necesidades de un cliente. Es fácil permitir que el plan impulse la implementación técnica, lo cual conduce a un esfuerzo de desarrollo centrado en las características. A menudo, este enfoque conduce a la satisfacción temporal de las partes interesadas, pero reduce la probabilidad de impulsar una innovación que surta efecto en los comportamientos de los clientes.
- Empatía con el cliente: los planes iniciales son una parte importante del aspecto empresarial del desarrollo y deben incluirse en los informes normales. Sin embargo, el aprendizaje, medición y creación con la empatía del cliente es una medida más adecuada de éxito en un esfuerzo de innovación. Centrarse en el cliente en lugar de en las características tiene más probabilidades de dar lugar a una satisfacción de los clientes a corto y largo plazo, y a un impacto empresarial.

**Ámbito mínimo:** la metodología de innovación muestra cómo integrar la estrategia y los planes mediante el consenso sobre el valor empresarial. En la guía se presentan, a continuación, las herramientas nativas de la nube que pueden acelerar cada materia de innovación, junto con los procedimientos recomendados para su implementación. Por último, en la sección de mejoras de procesos se muestran enfoques para la creación de empatía con el cliente al tiempo que se respetan los planes y estrategias del recorrido de adopción de la nube. Este enfoque se centra en ofrecer innovación con el uso de la menor tecnología posible.

**Ejemplo de ámbito ampliado:** en ocasiones, una innovación puede depender de cargas de trabajo críticas o de alta confidencialidad. Cuando el "cliente" es un usuario interno, el esfuerzo de desarrollo puede ser crítico o de alta confidencialidad durante las primeras iteraciones. En estos casos, se recomienda que los equipos de adopción utilicen el examen de la arquitectura de Azure y el marco de arquitectura de Azure para evaluar el diseño avanzado de la arquitectura en una fase temprana del proceso.

## <a name="balance-during-govern"></a>Equilibrio durante el gobierno

La práctica de la gobernanza en la nube es un equilibrio constante entre dos prioridades contrapuestas: velocidad y agilidad, y un entorno bien gobernado. El equipo de gobernanza en la nube se centra en evaluar y minimizar los riesgos para la empresa mediante controles uniformes y la reducción de los cambios. El equipo de adopción se centra en impulsar resultados empresariales, los cuales requieren nuevos riesgos y generan cambios de forma inherente.

**Prioridades contrapuestas:**

- Bien gobernado: cada control diseñado para minimizar el riesgo bloquea algún aspecto de cambio o limita las opciones de diseño. El control es esencial para un entorno bien gobernado. Sin embargo, cuando los controles se diseñan e implementan de manera aislada, pueden ser tan perjudiciales como los riesgos que pretenden evitar.
- Velocidad y agilidad: la velocidad y la agilidad son requisitos empresariales fundamentales en la economía digital. Ambos requieren la posibilidad de impulsar el cambio con elementos de bloqueo mínimos para la innovación o la adopción. Si se impulsa el cambio de manera aislada con respecto a la gobernanza, se generan nuevos riesgos que podrían perjudicar a la empresa de maneras no deseadas.

**Ámbito mínimo:** la metodología de gobierno recomienda que ni la gobernanza ni la adopción deben darse de manera aislada. Esta metodología comienza con una comprensión de las materias de gobernanza y una conversación en torno al riesgo empresarial, las directivas y el proceso de negocio. Como miembro activo a lo largo del recorrido de adopción de la nube, el equipo de gobernanza puede implementar un conjunto mínimo de límites de protección para afrontar los riesgos tangibles en el plan de adopción de la nube. Con el tiempo, el equipo de gobernanza puede refactorizar y expandir esos límites para afrontar nuevos riesgos. Este enfoque maximiza el aprendizaje y la innovación, al tiempo que reduce al mínimo el riesgo.

**Ejemplo de ámbito ampliado:** cuando el riesgo empresarial es alto, especialmente al principio del proceso de adopción, es posible que el equipo de gobernanza en la nube necesite acelerar la expansión de las implementaciones de gobernanza. Se pueden usar las mismas instrucciones y ejercicios para agregar este nivel de gobernanza más elevado, pero puede que sea necesario acelerar la programación temporal. En algunos escenarios, incluso puede ser necesario un estado avanzado de gobernanza durante la implementación de las primeras zonas de aterrizaje.

## <a name="balance-during-manage"></a>Equilibrio durante la administración

El modelo empresarial de TI con respecto a la administración de operaciones ha evolucionado continuamente durante la última década. A medida que el mantenimiento del hardware se aleja de la principal propuesta de valor de TI, la perspectiva sobre la administración de operaciones también cambia. A medida que TI aumenta su interés en proporcionar valor empresarial, los equipos de administración de operaciones entran en conflicto a la hora de alcanzar un equilibrio entre realizar inversiones para entornos con pocas operaciones, o sin ellas, frente a grandes inversiones.

**Prioridades contrapuestas:**

- Grandes inversiones: invertir por igual en la prevención de interrupciones, la recuperación rápida y la supervisión en todo el entorno es el enfoque tradicional en la administración de operaciones. Este enfoque puede ser costoso y, a veces, conlleva la duplicación de los productos de soporte que pone a disposición el proveedor de la nube.
- Sin operaciones o con pocas operaciones: aproveche las herramientas operativas nativas en la nube para reducir al mínimo las tareas repetitivas y recurrentes que ya entregaron previamente los empleados a tiempo completo. La reducción de estas dependencias operativas en el modelo de administración de operaciones permite a esos empleados generar más valor. Por sí solo, este enfoque puede conducir a un soporte de las operaciones de poca calidad.

**Ámbito mínimo:** la metodología de administración sugiere el establecimiento de una línea de base de administración nativa en la nube, sin operaciones. El reconocimiento de que la línea de base sin operaciones no satisface todas las necesidades empresariales impulsa a la empresa a definir los compromisos y adecuar mejor las inversiones. Amplíe la línea de base para satisfacer las necesidades comunes de todas las cargas de trabajo. A continuación, cree equipos de plataforma o de cargas de trabajo específicas para mantener soluciones bien administradas en un entorno bien administrado.

**Ejemplo de ámbito ampliado:** en la mayoría de los entornos, hay un pequeño porcentaje de cargas de trabajo cuyo valor empresarial justifica grandes inversiones en operaciones por parte de TI. En estos casos, es posible que el equipo de TI desee aprovechar el examen de la arquitectura de Azure y el marco de arquitectura de Azure para guiar las operaciones más complejas.

## <a name="balance-during-organize"></a>Equilibrio durante la organización

Las prioridades contrapuestas que aparecen a lo largo de este artículo son reflejo del intento por parte de TI de satisfacer las demandas empresariales para ganar velocidad y agilidad. Este mismo cambio aparece en los cambios realizados en los organigramas (o estructuras del equipo virtual) para proporcionar un respaldo mayor y lograr resultados comerciales. A medida que los directivos de TI influyen en las estructuras de equipo, normalmente se abordan dos prioridades contrapuestas: control centralizado frente a control delegado

**Prioridades contrapuestas:**

- Control centralizado: los modelos operativos con control centralizado conceden mayor importancia a la centralización de todos los controles necesarios para aplicar directivas rígidas. En este modelo, el departamento de TI actúa como un elemento de bloqueo de la innovación, la velocidad y la agilidad. En cambio, permite a TI garantizar un mayor grado de estabilidad, cumplimiento y seguridad.
- Control delegado: en este modelo operativo distribuido, se supone que cada equipo de desarrollo y operaciones, o equipo de aplicaciones empresariales, proporcionará su propio conjunto de controles en función de las soluciones necesarias para lograr los objetivos empresariales. Según este modelo, TI proporciona límites de protección para ayudar a mantener los equipos en la dirección adecuada, pero minimiza el número de restricciones técnicas forzadas siempre que es posible.

**Ámbito mínimo:** la mayoría de las organizaciones experimentarán un conjunto natural de evoluciones a lo largo del tiempo. La metodología de organización describe la serie de evoluciones más habitual. La recomendación para los equipos es intentar pasar a una estructura de Centro de excelencia en la nube que proporcione enfoques de control delegado.

**Ejemplo de ámbito ampliado:** hay muchas situaciones que podrían desencadenar la necesidad de un control centralizado. Dos ejemplos de desencadenadores del control centralizado podrían ser los requisitos de cumplimiento de terceros o los riesgos de seguridad temporales. En estas situaciones, normalmente es necesario establecer directivas de limitación y controles fijos y rígidos. Sin embargo, para permitir que la innovación y la adopción continúen, se recomienda que los equipos de TI centrales proporcionen esos controles en función de la importancia y la confidencialidad de cada carga de trabajo. Proporcionar entornos con menor control, pero con un ámbito o perfil de riesgos reducido, permite una mayor flexibilidad incluso cuando se necesita control.

## <a name="next-steps"></a>Pasos siguientes

Aprenda a [equilibrar migración, innovación y experimentación](./balance-the-portfolio.md) para maximizar el valor de los esfuerzos de migración a la nube.

> [!div class="nextstepaction"]
> [Equilibrio de la cartera](./balance-the-portfolio.md)
