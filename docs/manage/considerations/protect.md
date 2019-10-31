---
title: 'Protección y recuperación: Administración y operaciones en la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Protección y recuperación: Administración y operaciones en la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 2e055cb6105b9424259d2b8e86bdde7d64798479
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72682450"
---
# <a name="protect-and-recover-in-cloud-management"></a>Protección y recuperación en la administración de la nube

Una vez que se han cumplido los requisitos de [inventario y visibilidad](./inventory.md) y de [cumplimiento operativo](./operational-compliance.md), los equipos de administración de la nube se pueden preparar para la posibilidad de una interrupción en una carga de trabajo. Cuando se planea la administración de la nube, el equipo debe plantearse la posibilidad de que se produzca un error.

No hay ninguna solución técnica que pueda ofrecer constantemente un Acuerdo de Nivel de Servicio de tiempo de actividad del 100 %. Aquellas soluciones con las arquitecturas más redundantes afirman que pueden ofrecer un tiempo de actividad de "seis nueves", es decir, del 99,9999 %. Pero incluso estas soluciones dejan de funcionar durante 31,6 segundos como mínimo cada año. Además, lamentablemente, pocas soluciones justifican la gran inversión constante que se necesita para alcanzar el 99,9999 % de tiempo de actividad.

La preparación ante las interrupciones permitirá que el equipo detecte errores antes y se recupere más rápidamente. El enfoque de esta materia se centra en los pasos siguientes que hay que tomar después de un error del sistema. ¿Cómo se protegen las cargas de trabajo para que se puedan recuperar rápidamente cuando se produce una interrupción?

## <a name="translating-protection-and-recovery-conversations"></a>Descripción de las conversaciones sobre protección y recuperación

Las cargas de trabajo que impulsan las operaciones empresariales constan de aplicaciones, datos, máquinas virtuales y otros recursos. Cada uno de esos recursos puede requerir un enfoque diferente para la protección y la recuperación. Un aspecto importante de esta materia consiste en establecer un compromiso coherente dentro de la línea de base de administración para proporcionar un punto de partida para las conversaciones empresariales.

Como mínimo, cada recurso que respalda una carga de trabajo determinada debe disponer de un enfoque de línea de base con un compromiso claro relativo a la velocidad de recuperación (objetivos de tiempo de recuperación o RTO) y al riesgo de pérdida de datos (objetivos de punto de recuperación o RPO).

### <a name="recovery-time-objectives-rto"></a>Objetivos de tiempo de recuperación (RTO)

Cuando se produce un desastre, el RTO es la cantidad de tiempo que debe tardar un sistema determinado en recuperar su estado previo al desastre. Para cada carga de trabajo, esto incluye el tiempo requerido para restaurar la funcionalidad mínima necesaria de las máquinas virtuales y las aplicaciones. También incluye el tiempo necesario para restaurar los datos que requieren las aplicaciones.

En términos empresariales, el RTO representa la cantidad de tiempo que un proceso de negocio estará fuera de servicio. En el caso de cargas de trabajo críticas, esta variable debe ser relativamente baja para permitir que los procesos se reanuden rápidamente. Para aquellas cargas de trabajo de prioridad baja, es posible que un nivel estándar de RTO no afecte notablemente al rendimiento de la empresa.

La línea de base de administración debe establecer un objetivo de tiempo de recuperación estándar para las cargas de trabajo no críticas. Posteriormente, la empresa puede usar esa línea de base como una manera de justificar inversiones adicionales en los tiempos de recuperación.

### <a name="recovery-point-objectives-rpo"></a>Objetivos de punto de recuperación (RPO)

En la mayoría de los sistemas de administración de la nube, los datos se capturan y almacenan periódicamente mediante algún tipo de protección de datos. La última vez que se capturaron los datos se conoce como punto de recuperación. Cuando se produce un error en un sistema, solo se puede restaurar al punto de recuperación más reciente.

Si un sistema tiene un objetivo de punto de recuperación que se mide en horas o días, un error del sistema daría lugar a la pérdida de datos durante esas horas o días que transcurren entre el último punto de recuperación y la interrupción. En teoría, un RPO de 1 día dará lugar a la pérdida de todas las transacciones del día en que se produjo el error.

En el caso de sistemas críticos, un RPO medido en minutos o segundos será más adecuado para evitar una pérdida de ingresos. Sin embargo, un RPO más corto suele provocar un aumento de los costos generales de administración.

Una línea de base de administración debe concentrarse en hallar el RPO más largo aceptable para minimizar los costos. El equipo de administración de la nube puede aumentar el RPO de plataformas o cargas de trabajo concretas, lo que justificaría una mayor inversión.

## <a name="protect-and-recover-workloads"></a>Protección y recuperación de cargas de trabajo

La mayoría de las cargas de trabajo de un entorno de TI admiten un proceso de negocio o técnico muy pequeño. Los sistemas que no tienen un impacto sistémico en las operaciones empresariales a menudo no justifican el aumento de las inversiones que se necesita para una recuperación rápida o la reducción al mínimo de la pérdida de datos. El establecimiento de una línea de base permite a las empresas comprender claramente qué nivel de respaldo a la recuperación se puede ofrecer a cambio de un precio concreto y asumible. Esto ayuda a las partes interesadas de la empresa a evaluar el valor de una mayor inversión en los procesos de recuperación.

Para la mayoría de los equipos de administración de la nube, una línea de base mejorada con compromisos específicos de RPO/RTO para varios recursos, genera el escenario más favorable para establecer compromisos empresariales mutuos. En las secciones siguientes se describen algunas líneas de base mejoradas comunes que permiten a la empresa agregar fácilmente funcionalidades de protección y recuperación mediante un proceso repetible.

### <a name="protect-and-recover-data"></a>Protección y recuperación de datos

Los datos son posiblemente el recurso más valioso en la economía digital. La capacidad para proteger y recuperar datos de forma más eficaz es la línea de base mejorada más común. En el caso de los datos que forman parte de una carga de trabajo de producción, la pérdida de datos se puede equiparar directamente a una pérdida de ingresos o de rentabilidad. Por lo general, se recomienda que los equipos de administración de la nube ofrezcan un nivel de línea de base de administración mejorada que admita plataformas de datos comunes.

Antes de implementar operaciones de plataforma, es habitual que los equipos de administración de la nube respalden operaciones mejoradas para los datos de plataforma como servicio. Por ejemplo, es fácil que un equipo de administración de la nube aplique una mayor frecuencia de copias de seguridad o de replicación en varias regiones para las soluciones de Azure SQL o Cosmos DB. Esto permite que el equipo de desarrollo pueda mejorar fácilmente el RPO simplemente modernizando sus plataformas de datos.

Este razonamiento se volverá a analizar más detalladamente en la [materia sobre operaciones de la plataforma](./platform.md).

### <a name="protect-and-recover-vms"></a>Protección y recuperación de máquinas virtuales

La mayoría de las cargas de trabajo tienen alguna dependencia de las máquinas virtuales. Esas máquinas virtuales hospedan diversos aspectos de la solución. Para que la carga de trabajo apoye un proceso empresarial después de un error del sistema, es necesario recuperar rápidamente una parte de esas máquinas virtuales.

Cada minuto de tiempo de inactividad de esas máquinas virtuales conlleva una pérdida de ingresos o una menor rentabilidad. Cuando el tiempo de inactividad de las máquinas virtuales tiene un impacto directo en el rendimiento fiscal de la empresa, el RTO pasa a ser algo muy importante. Las máquinas virtuales se pueden recuperar más rápidamente mediante la replicación en un sitio secundario y la recuperación automatizada, este modelo se conoce como modelo de recuperación activa-semiactiva. En un estado ideal de recuperación, las máquinas virtuales se pueden replicar en un sitio secundario totalmente funcional. Este enfoque más caro se conoce como modelo de recuperación activa-activa o de alta disponibilidad.

Cada uno de los modelos anteriores reduce el objetivo de tiempo de recuperación, lo que da lugar a una restauración más rápida de las funcionalidades del proceso de negocio. Sin embargo, cada modelo también supone un aumento considerable de los costos de administración de la nube.

Este razonamiento se volverá a analizar más detalladamente en la [materia sobre operaciones con cargas de trabajo](./workload.md).

## <a name="next-steps"></a>Pasos siguientes

Una vez satisfecho este componente de la línea de base de administración, el equipo puede prepararse para evitar interrupciones mediante las [operaciones de la plataforma](./platform.md) y las [operaciones con cargas de trabajo](./workload.md).

> [!div class="nextstepaction"]
> [Operaciones de la plataforma](./platform.md)
> [Operaciones con cargas de trabajo](./workload.md)
