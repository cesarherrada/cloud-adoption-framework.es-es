---
title: Protección y recuperación en la administración de la nube
description: Conozca la importancia de prepararse para una posible interrupción de la carga de trabajo. Esta preparación permite que el equipo detecte los errores antes y se recupere más rápidamente.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: f46fb65572d319e2dc9a4a779cd205bbe476908b
ms.sourcegitcommit: 0ea426f2f471eb7310c6f09478be1306cf7bf0d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "78341002"
---
# <a name="protect-and-recover-in-cloud-management"></a>Protección y recuperación en la administración de la nube

Después de cumplir los requisitos de [inventario y visibilidad](./inventory.md) y de [cumplimiento operativo](./operational-compliance.md), los equipos de administración de la nube se pueden anticipar y prepararse para una posible interrupción de la carga de trabajo. Cuando planean la administración de la nube, los equipos deben plantearse la posibilidad de que se produzca un error.

No hay ninguna solución técnica que pueda ofrecer constantemente un Acuerdo de Nivel de Servicio de tiempo de actividad del 100 %. Aquellas soluciones con las arquitecturas más redundantes afirman que pueden ofrecer un tiempo de actividad de "seis nueves", es decir, del 99,9999 %. Pero incluso estas soluciones dejan de funcionar durante 31,6 segundos como mínimo cada año. Además, es raro que una solución justifique la gran inversión operativa constante que se necesita para alcanzar un tiempo de actividad de "seis nueves".

La preparación ante las interrupciones permite que el equipo detecte errores antes y se recupere más rápidamente. El enfoque de esta materia se centra en los pasos siguientes que hay que tomar inmediatamente después de un error del sistema. ¿Cómo se protegen las cargas de trabajo para que se puedan recuperar rápidamente cuando se produce una interrupción?

## <a name="translate-protection-and-recovery-conversations"></a>Traslado de las conversaciones sobre protección y recuperación

Las cargas de trabajo que impulsan las operaciones empresariales constan de aplicaciones, datos, máquinas virtuales (VM) y otros recursos. Cada uno de esos recursos puede requerir un enfoque diferente para la protección y la recuperación. Un aspecto importante de esta materia consiste en establecer un compromiso coherente dentro de la base de referencia de administración, que puede proporcionar un punto de partida durante las conversaciones empresariales.

Como mínimo, cada recurso que respalda una carga de trabajo determinada debe disponer de un enfoque de base de referencia con un compromiso claro relativo a la velocidad de recuperación (objetivos de tiempo de recuperación o RTO) y al riesgo de pérdida de datos (objetivos de punto de recuperación o RPO).

### <a name="recovery-time-objectives-rto"></a>Objetivos de tiempo de recuperación (RTO)

Cuando se produce un desastre, el objetivo de tiempo de recuperación es la cantidad de tiempo que debe tardar cualquier sistema en recuperar su estado previo al desastre. Para cada carga de trabajo, esto incluye el tiempo requerido para restaurar la funcionalidad mínima necesaria de las máquinas virtuales y las aplicaciones. También incluye el tiempo necesario para restaurar los datos que requieren las aplicaciones.

En términos empresariales, el RTO representa la cantidad de tiempo que un proceso de negocio estará fuera de servicio. En el caso de cargas de trabajo críticas, esta variable debe ser relativamente baja para permitir que los procesos se reanuden rápidamente. Para aquellas cargas de trabajo de prioridad baja, es posible que un nivel estándar de RTO no afecte notablemente al rendimiento de la empresa.

La base de referencia de administración debe establecer un objetivo de tiempo de recuperación estándar para las cargas de trabajo no críticas. Posteriormente, la empresa puede usar esa línea de base como una manera de justificar inversiones adicionales en los tiempos de recuperación.

### <a name="recovery-point-objectives-rpo"></a>Objetivos de punto de recuperación (RPO)

En la mayoría de los sistemas de administración de la nube, los datos se capturan y almacenan periódicamente mediante algún tipo de protección de datos. La última vez que se capturaron los datos se conoce como punto de recuperación. Cuando se produce un error en un sistema, solo se puede restaurar al punto de recuperación más reciente.

Si un sistema tiene un objetivo de punto de recuperación que se mide en horas o días, un error del sistema daría lugar a la pérdida de datos durante esas horas o días que transcurren entre el último punto de recuperación y la interrupción. En teoría, un RPO de 1 día dará lugar a la pérdida de todas las transacciones del día en que se produjo el error.

En el caso de sistemas críticos, un RPO medido en minutos o segundos puede ser más adecuado para evitar una pérdida de ingresos. Sin embargo, un RPO más corto suele provocar un aumento de los costos generales de administración.

Una base de referencia de administración debe concentrarse en hallar el RPO más largo aceptable para minimizar los costos. El equipo de administración de la nube puede aumentar el RPO de plataformas o cargas de trabajo concretas, lo que justificaría una mayor inversión.

## <a name="protect-and-recover-workloads"></a>Protección y recuperación de cargas de trabajo

La mayoría de las cargas de trabajo de un entorno de TI respaldan un proceso empresarial o técnico concreto. Los sistemas que no tienen un impacto sistémico en las operaciones empresariales a menudo no justifican el aumento de las inversiones que se necesita para una recuperación rápida o la reducción al mínimo de la pérdida de datos. El establecimiento de una base de referencia permite a las empresas comprender claramente qué nivel de respaldo a la recuperación se puede ofrecer a cambio de un precio concreto y asumible. Ello ayuda a las partes interesadas de la empresa a evaluar el valor de una mayor inversión en los procesos de recuperación.

Para la mayoría de los equipos de administración de la nube, una base de referencia mejorada con compromisos específicos de RPO/RTO para varios recursos, genera el escenario más favorable para establecer compromisos empresariales mutuos. En las secciones siguientes se describen algunas líneas de base mejoradas comunes que permiten a la empresa agregar fácilmente funcionalidades de protección y recuperación mediante un proceso repetible.

### <a name="protect-and-recover-data"></a>Protección y recuperación de datos

Los datos son posiblemente el recurso más valioso en la economía digital. La capacidad para proteger y recuperar datos de forma más eficaz es la línea de base mejorada más común. En el caso de los datos que forman parte de una carga de trabajo de producción, la pérdida de datos se puede equiparar directamente a una pérdida de ingresos o de rentabilidad. Por lo general, se recomienda que los equipos de administración de la nube ofrezcan un nivel de base de referencia de administración mejorada que admita las plataformas de datos comunes.

Antes de que los equipos de administración de la nube implementen operaciones de plataforma, es habitual que respalden las operaciones mejoradas de una plataforma de datos como servicio (PaaS). Por ejemplo, es fácil que un equipo de administración de la nube aplique una mayor frecuencia de copias de seguridad o de replicación en varias regiones para las soluciones de Azure SQL Database o Azure Cosmos DB. Esto permite que el equipo de desarrollo pueda mejorar fácilmente el RPO mediante la modernización de sus plataformas de datos.

Para obtener más información acerca de este proceso de reflexión, consulte la [materia sobre operaciones de plataforma](./platform.md).

### <a name="protect-and-recover-vms"></a>Protección y recuperación de máquinas virtuales

La mayoría de las cargas de trabajo tienen alguna dependencia de las máquinas virtuales, que hospedan diversos aspectos de la solución. Para que la carga de trabajo apoye un proceso empresarial después de un error del sistema, es necesario recuperar rápidamente varias máquinas virtuales.

Cada minuto de tiempo de inactividad de esas máquinas virtuales puede provocar una pérdida de ingresos o una menor rentabilidad. Cuando el tiempo de inactividad de la VM tiene un impacto directo en el rendimiento fiscal de la empresa, el RTO pasa a ser algo muy importante. Las máquinas virtuales se pueden recuperar más rápidamente mediante la replicación en un sitio secundario y la recuperación automatizada, un modelo que se conoce como modelo de recuperación activa-semiactiva. En un estado ideal de recuperación, las máquinas virtuales se pueden replicar en un sitio secundario totalmente funcional. Este enfoque más caro se conoce como modelo de recuperación activa-activa o de alta disponibilidad.

Cada uno de los modelos anteriores reduce el RTO, lo que da lugar a una restauración más rápida de las funcionalidades del proceso de negocio. Sin embargo, cada modelo también supone un aumento considerable de los costos de administración de la nube.

Para obtener más información acerca de este proceso de reflexión, consulte la [materia sobre operaciones de carga de trabajo](./workload.md).

## <a name="next-steps"></a>Pasos siguientes

Una vez satisfecho este componente de la línea de base de administración, el equipo puede prepararse para evitar interrupciones en las [operaciones de la plataforma](./platform.md) y las [operaciones con cargas de trabajo](./workload.md).

> [!div class="nextstepaction"]
> [Operaciones de la plataforma](./platform.md)
> [Operaciones con cargas de trabajo](./workload.md)
