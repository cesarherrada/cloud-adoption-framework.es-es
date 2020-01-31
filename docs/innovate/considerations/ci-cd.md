---
title: 'Innovación en la nube: Capacitación para la adopción'
description: 'Introducción a la innovación en la nube: capacitación para la adopción'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: a3c726443e62140dba997ae4a1ff89593f72e6e6
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76808522"
---
# <a name="empower-adoption"></a>Capacitación para la adopción

La prueba definitiva de la innovación es la reacción de los clientes a su invención. ¿Se ha demostrado la hipótesis? ¿Los clientes usan la solución? ¿Se puede escalar para satisfacer las necesidades del porcentaje de usuarios deseado? Lo más importante, ¿siguen volviendo? No se puede realizar ninguna de estas preguntas hasta que se haya implementado la solución de producto mínimo viable (MVP). En este artículo, nos centraremos en la materia de capacitación para la adopción.

## <a name="reduce-friction-that-affects-adoption"></a>Reducción de la fricción que afecta a la adopción

Hay algunos puntos de fricción importantes en la adopción que se pueden minimizar con una combinación de tecnología y procesos. Para lectores con conocimientos de integración continua (CI) y procesos de implementación continua (CD) o DevOps, lo siguiente le resultará familiar. En este artículo se establece un punto de partida para los equipos de adopción de la nube que ayuda con los bucles de innovación y comentarios. En el futuro, este punto de partida podría fomentar enfoques de CI/CD o DevOps más sólidos a medida que los productos y equipos se consoliden.

Tal y como se describe en [Medida del impacto en los clientes](./measure.md), una validación positiva de cualquier hipótesis requiere iteración y determinación. Experimentará muchos más errores que aciertos durante los ciclos de innovación. Se espera que esto sea así. Sin embargo, cuando se alinean a escala la necesidad del cliente, la hipótesis y la solución, todo cambia rápidamente. El objetivo de este artículo es minimizar la [demanda técnica](./build.md#reduce-complexity-and-delay-technical-spikes) que ralentiza la innovación y, al mismo tiempo, asegurarse de implementar algunos procedimientos recomendados sólidos. Si lo hace, ayudará a que el diseño del equipo tenga éxito en el futuro, al mismo tiempo que satisface las necesidades actuales de los clientes.

## <a name="empowering-adoption-the-maturity-model"></a>Capacitación para la adopción: modelo de madurez

El objetivo principal de la [metodología de innovación](./index.md) es crear asociaciones con los clientes y acelerar los bucles de comentarios, lo que dará lugar a innovaciones en el mercado. En la imagen y las secciones siguientes se describen las implementaciones iniciales que apoyan esta metodología.

![Capacitación para la adopción: modelo de madurez](../../_images/innovate/empower-adoption-maturity.png)

- [Solución compartida:](#shared-solution) establezca un repositorio centralizado para todos los aspectos de la solución.
- [Bucles de comentarios:](#feedback-loops) asegúrese de que los bucles de comentarios se pueden administrar de forma coherente mediante iteraciones.
- [Integración continua:](#continuous-integration) compile la solución y consolídela con regularidad.
- [Pruebas confiables:](#reliable-testing) valide la calidad de la solución y los cambios previstos para garantizar la confiabilidad de las métricas de pruebas.
- [Implementación de la solución:](#solution-deployment) implemente soluciones para que el equipo pueda compartir rápidamente los cambios con los clientes.
- [Medida integrada:](#integrated-measurements) agregue métricas de aprendizaje al bucle de comentarios para que el equipo completo los analice.

Para minimizar las demandas técnicas, dé por hecho que la madurez de cada uno de estos principios será baja inicialmente. No obstante, para trazar un plan definitivo con antelación, realice la alineación con herramientas y procesos que se puedan escalar a medida que las hipótesis sean más específicas. En Azure, [GitHub](https://guides.github.com) y [Azure DevOps](https://docs.microsoft.com/azure/devops) permiten a los equipos pequeños empezar a trabajar con poca fricción. Estos equipos pueden crecer hasta incluir a miles de desarrolladores que colaboran en soluciones a escala y prueban cientos de hipótesis de clientes. En el resto de este artículo se ilustra el enfoque "planea a lo grande, da pasos pequeños" para posibilitar la adopción de cada uno de estos principios.

## <a name="shared-solution"></a>Solución compartida

Tal y como se describe en [Medida del impacto en los clientes](./measure.md), una validación positiva de cualquier hipótesis requiere iteración y determinación. Experimentará muchos más errores que aciertos durante los ciclos de innovación. Se espera que esto sea así. Sin embargo, cuando se alinean a escala la necesidad del cliente, la hipótesis y la solución, todo cambia rápidamente.

Al escalar la innovación, la herramienta más valiosa es una base de código compartida para la solución. Lamentablemente, no hay ninguna manera confiable de predecir qué iteración o producto viable mínimo será la combinación ganadora. Esta es la razón por la que nunca es demasiado pronto para establecer una base de código base o un repositorio compartido. Esta es la única [demanda técnica](./build.md#reduce-complexity-and-delay-technical-spikes) que nunca se debe retrasar. A medida que el equipo itera por las distintas soluciones de producto viable mínimo, un repositorio compartido facilita colaboración y acelera el desarrollo. Cuando los cambios en la solución minan las métricas de aprendizaje, el control de versiones le permite revertir a una versión anterior y más efectiva de la solución.

La herramienta más adoptada para administrar los repositorios de código es [GitHub](https://guides.github.com), que permite la creación de un repositorio de código compartido con unos pocos clics. Como alternativa, se puede usar la característica [Azure Repos](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops) de Azure DevOps para crear un [Git](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops#git) o repositorio de [Team Foundation](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops#tfvc).

## <a name="feedback-loops"></a>Bucles de comentarios

Hacer que el cliente forme parte de la solución es la clave para crear asociaciones con los clientes durante los ciclos de innovación. Esto se logra, en parte, [midiendo el impacto del cliente](./measure.md). Requiere conversaciones y pruebas directas con el cliente. Ambos generan comentarios que se deben administrar de forma eficaz.

Cada comentario es una posible solución a las necesidades del cliente. Lo que es más importante, cada uno de los comentarios directos de un cliente representa una oportunidad para mejorar la relación. Si los comentarios permiten dar con la solución viable mínima, celébrelo con el cliente. Aunque algunos comentarios no sean accionables, ser transparentes con la decisión de reducir la prioridad de los comentarios demuestra una [mentalidad de crecimiento](./learn.md#growth-mindset) y una atención en el [aprendizaje continuo](./learn.md#continuous-learning).

[Azure DevOps](https://docs.microsoft.com/azure/devops) incluye maneras de [solicitar, proporcionar y administrar comentarios](https://docs.microsoft.com/azure/devops/project/feedback). Cada una de estas herramientas centraliza los comentarios para que el equipo pueda tomar medidas y proporcionar seguimiento en servicio de un bucle de comentarios transparente.

## <a name="continuous-integration"></a>Integración continua

A medida que la adopción escala y la hipótesis se aproxima a una verdadera innovación a escala, el número de pequeñas hipótesis que hay que probar tiende a crecer rápidamente. Para facilitar bucles de comentarios precisos y procesos de adopción fluidos, es importante que cada una de esas hipótesis se integre y respalde la hipótesis principal que subyace a la innovación. Esto significa que también tiene que moverse rápidamente para innovar y crecer, lo que requiere que varios desarrolladores prueben variantes de la hipótesis principal. En los trabajos de desarrollo de fases posteriores, es posible que necesite varios equipos de desarrolladores que colaboren en la creación de una solución compartida. La integración continua es el primer paso para la administración de todas las partes móviles.

En la integración continua, los cambios de código se combinan con frecuencia en la rama principal. Los procesos automatizados de compilación y pruebas garantizan que el código de la rama principal siempre tenga una calidad de producción. Esto permite que los desarrolladores trabajen juntos para desarrollar soluciones compartidas que proporcionen bucles de comentarios precisos y confiables.

Azure DevOps y [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines) proporcionan funcionalidades de integración continua con unos pocos clics en GitHub o en otros repositorios.
Obtenga más información acerca de la [integración continua](https://docs.microsoft.com/azure/devops/learn/what-is-continuous-integration) o consulte el [laboratorio práctico](https://www.azuredevopslabs.com/labs/azuredevops/continuousintegration) para obtener más información. También hay arquitecturas de soluciones para acelerar la creación de sus [canalizaciones de CI/CD a través de Azure DevOps](https://azure.microsoft.com/solutions/devops).

## <a name="reliable-testing"></a>Pruebas confiables

Los defectos de cualquier solución pueden crear falsos positivos o falsos negativos. Los errores inesperados pueden dar lugar a una interpretación incorrecta de las métricas de adopción de los usuarios. También pueden generar comentarios negativos de los clientes que no representen con precisión la demostración de su hipótesis.

Durante las iteraciones en las fases tempranas de una solución mínima viable, se esperan defectos; los primeros en adoptarla podrían incluso encontrarlos simpáticos. En las primeras versiones, no suelen existir pruebas de aceptación. Sin embargo, uno de los aspectos de la creación con empatía está relacionado con la validación de la necesidad y la hipótesis. Ambas se pueden realizar mediante pruebas unitarias en el nivel de código y pruebas de aceptación manuales antes de la implementación. En conjunto, proporcionan medios para confiar en las pruebas. Debe procurar automatizar una serie bien definida de pruebas de compilación, unitarias y de aceptación. Esto garantizará métricas confiables relacionadas con ajustes más pormenorizados de la hipótesis y la solución resultante.

La característica [Azure Test Plans](https://docs.microsoft.com/azure/devops/test/track-test-status?view=azure-devops) proporciona herramientas para desarrollar y utilizar planes de pruebas durante la ejecución de pruebas manuales o automatizadas.

## <a name="solution-deployment"></a>Implementación de la solución

Quizás el aspecto más significativo de la capacitación para la adopción es la posibilidad de controlar el lanzamiento de una solución a los clientes. Proporcionar una canalización de autoservicio o automatizada para lanzar una solución a los clientes acelera el bucle de comentarios. Permitir a los clientes interactuar con los cambios en la solución rápidamente les invita a participar en el proceso. Este enfoque también desencadena pruebas más rápidas de las hipótesis, lo que reduce las suposiciones y las posibles repeticiones del trabajo.

Existen varios métodos para la implementación de soluciones. A continuación se indican los tres métodos más comunes:

- La **implementación continua** es el enfoque más avanzado, ya que implementa automáticamente los cambios de código en producción. Para los equipos experimentados que realizan pruebas de hipótesis más desarrolladas, la implementación continua puede ser muy valiosa.
- Durante las primeras fases del desarrollo, puede ser más adecuada la **entrega continua**. En la entrega continua, los cambios de código se implementan automáticamente en un entorno similar al de producción. Los desarrolladores, los responsables de la toma de decisiones empresariales y otros miembros del equipo pueden usar este entorno para comprobar si su trabajo está listo para producción. También puede usar este método para probar una hipótesis con los clientes, sin que ello afecte a las actividades empresariales en curso.
- La **implementación manual** es el enfoque menos sofisticado para la administración de versiones. Como sugiere el nombre, alguien del equipo implementara manualmente los cambios de código más recientes. Este enfoque es propenso a errores, no confiable y considerado un antipatrón por los ingenieros más experimentados.

Durante la primera iteración de una solución mínima viable, es habitual la implementación manual a pesar de la valoración anterior. Cuando la solución es muy fluida y no se conocen los comentarios de los clientes, restablecer toda la solución (o incluso la hipótesis principal) supone un riesgo significativo. La regla general de la implementación manual es que no se realiza ninguna prueba de cliente ni automatización de la implementación.

Invertir pronto puede provocar pérdida de tiempo. Lo que es más importante, puede crear dependencias en la canalización de lanzamiento, lo que hace que el equipo sea más resistente a una dinamización temprana. Después de las primeras iteraciones o cuando los comentarios de los clientes sugieren un posible éxito, se debe adoptar rápidamente un modelo de implementación más avanzado.

En cualquier etapa de la validación de hipótesis, Azure DevOps y [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines) proporcionan funciones de entrega continua e implementación continua. Obtenga más información sobre la [entrega continua](https://docs.microsoft.com/azure/devops/learn/what-is-continuous-delivery) o consulte el [laboratorio práctico](https://www.azuredevopslabs.com/labs/azuredevops/continuousdeployment). La arquitectura de la solución también puede acelerar la creación de sus [canalizaciones de CI/CD a través de Azure DevOps](https://azure.microsoft.com/solutions/devops).

## <a name="integrated-measurements"></a>Medidas integradas

A la hora de [medir el impacto en el cliente](./measure.md), es importante comprender cómo reaccionan los clientes a los cambios en la solución. Estos datos, que se conocen como *telemetría*, proporcionan información detallada sobre las acciones que tomó un usuario (o una cohorte de usuarios) al trabajar con la solución. A partir de estos datos, es fácil obtener una validación cuantitativa de la hipótesis. Estas métricas se pueden usar para ajustar la solución y generar hipótesis más específicas. Estos cambios más sutiles ayudan a madurar la solución inicial en iteraciones posteriores, lo que impulsa la adopción a escala en última instancia.

En Azure, [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) proporciona herramientas y una interfaz para recopilar y revisar datos de las experiencias de los clientes. Puede aplicar dichas observaciones e información para refinar el trabajo pendiente mediante [Azure Boards](https://docs.microsoft.com/azure/devops/boards).

## <a name="next-steps"></a>Pasos siguientes

Una vez que comprenda las herramientas y los procesos necesarios para posibilitar la adopción, es el momento de examinar una materia de innovación más avanzada: la [interacción con dispositivos](./devices.md). Esta materia puede ayudar a reducir las barreras entre las experiencias física y digital, lo que facilita la adopción de la solución.

> [!div class="nextstepaction"]
> [Interacción con dispositivos](./devices.md)
