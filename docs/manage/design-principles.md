---
title: Aplicación de principios de diseño y operaciones avanzadas
description: Aplicación de principios de diseño y operaciones avanzadas
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 16762a0eae366c3bf1cd578faaf52df60e6c97b1
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76807689"
---
# <a name="apply-design-principles-and-advanced-operations"></a>Aplicación de principios de diseño y operaciones avanzadas

Las tres primeras materias de administración de la nube describen una línea de base de administración. Como mínimo, una línea de base de administración debe incluir un compromiso empresarial estándar para minimizar las interrupciones del negocio y acelerar la recuperación si se interrumpe el servicio. La mayoría de las líneas de base de administración incluyen una materia centrada en el mantenimiento del "inventario y visibilidad", el "cumplimiento operativo" y la "protección y recuperación".

El propósito de una línea base de administración es crear una oferta coherente que proporcione un nivel mínimo de compromiso empresarial para todas las cargas de trabajo que se admiten. Esta línea de base de ofertas de administración repetibles comunes permite al equipo ofrecer un grado de administración operativa altamente optimizado con una desviación mínima. Sin embargo, es posible que esa oferta estándar no ofrezca un compromiso suficientemente completo para la empresa.

En el diagrama de la siguiente sección se muestran tres maneras de ampliar la línea de base de administración.

La línea de base de administración debe cumplir el compromiso mínimo requerido por el 80 % de las cargas de trabajo de importancia crítica más baja de la cartera. La línea de base no se debe aplicar a las cargas de trabajo críticas. Tampoco debería aplicarse a plataformas comunes que se comparten entre cargas de trabajo. Esas cargas de trabajo requieren concentrarse en los principios de diseño y las operaciones avanzadas.

## <a name="advanced-operations-options"></a>Opciones de las operaciones avanzadas

Se recomiendan tres formas de mejorar los compromisos empresariales más allá de la línea de base de administración, como se indica en el siguiente diagrama:

![Operaciones avanzadas](../_images/manage/beyond-the-baseline.png)

## <a name="enhanced-management-baseline"></a>Línea de base de administración mejorada

Como se describe en la guía de administración de Azure, una línea de base de administración mejorada usa herramientas nativas en la nube para mejorar el tiempo de actividad y reducir los tiempos de recuperación. Las mejoras son sustanciales, pero menos que con la especialización de la carga de trabajo o la plataforma. La ventaja de una línea de base de administración mejorada es la reducción igualmente significativa en el costo y el tiempo de implementación.

## <a name="management-specialization"></a>Especialización de la administración

Hay diversos aspectos de las operaciones de carga de trabajo y plataforma que pueden requerir cambios en los principios de diseño y arquitectura. Estos cambios pueden tardar un tiempo y generar mayores gastos de funcionamiento. Para reducir el número de cargas de trabajo que requieren tales inversiones, una línea de base de administración mejorada podría proporcionar una mejora en el compromiso empresarial.

En el caso de las cargas de trabajo que justifican una mayor inversión para satisfacer un compromiso empresarial, la especialización de las operaciones es clave.

## <a name="areas-of-management-specialization"></a>Áreas de especialización de la administración

Hay dos áreas de especialización:

- **Especialización de la plataforma:** Se invierte en las operaciones en curso de una plataforma compartida, distribuyendo la inversión entre varias cargas de trabajo.
- **Especialización de la carga de trabajo:** Se invierte en las operaciones en curso de una carga de trabajo específica, normalmente reservada para cargas de trabajo críticas.

### <a name="central-it-or-cloud-center-of-excellence-ccoe"></a>TI centralizado o Centro de excelencia en la nube (CCoE)

Las decisiones entre la especialización de la plataforma y la especialización de la carga de trabajo se basan en el nivel de importancia crítica y en el impacto de cada carga de trabajo. No obstante, esta decisión también es indicativa de una decisión cultural de mayor envergadura entre los modelos organizativos de TI centralizado y de CCoE.

La especialización de carga de trabajo suele desencadenar un cambio en la cultura. Ambos modelos, TI tradicional y TI centralizado, crean procesos que pueden proporcionar soporte a escala. El soporte a escala es más factible para los servicios repetibles que se encuentran en una línea de base de administración, una línea de base mejorada o incluso en operaciones de plataforma. La especialización de la carga de trabajo no suele escalarse. Esta falta de escalado dificulta que una organización de TI centralizado proporcione el soporte necesario sin alcanzar los límites organizativos de escalado.

Como alternativa, el enfoque con un Centro de excelencia en la nube se escala mediante una delegación intencionada de la responsabilidad y una centralización selectiva. La especialización de la carga de trabajo tiende a alinearse mejor con el enfoque de responsabilidad delegada de un CCoE.

A continuación, se describe la alineación natural de los roles de un CCoE.

- El equipo de plataforma de la nube ayuda a crear plataformas comunes que admiten varios equipos de adopción de la nube.
- El equipo de automatización de la nube extiende esas plataformas a los recursos que se pueden implementar en un catálogo de servicios.
- La administración de la nube ofrece la base de referencia de administración de forma centralizada y ayuda a admitir el uso del catálogo de servicios.
- Sin embargo, la unidad de negocio (en forma de equipo de DevOps empresarial o equipo de adopción de la nube) mantiene la responsabilidad de las operaciones cotidianas de carga de trabajo, canalización o rendimiento.

A la hora de alinear áreas de administración, los modelos de TI centralizado y de CCoE generalmente pueden ofrecer una especialización de plataforma, con un cambio cultural mínimo. Proporcionar una especialización de la carga de trabajo puede ser un poco más complejo para los equipos de TI centralizados.

## <a name="management-specialization-processes"></a>Procesos de especialización de la administración

Dentro de cada especialización, el siguiente proceso de cuatro pasos se ofrece en un enfoque iterativo disciplinado. Este enfoque requiere la asociación con expertos de adopción de la nube, plataforma en la nube, automatización en la nube y administración de la nube para crear un bucle de comentarios práctico e informado.

- **Mejora del diseño del sistema:** se mejora el diseño de sistemas comunes (plataformas) o cargas de trabajo específicas para minimizar las interrupciones de forma eficaz.
- **Corrección automática:** algunas mejoras no son rentables. En tales casos, es posible que tenga más sentido automatizar la corrección y reducir el impacto de las interrupciones.
- **Escalado de la solución:** a medida que se mejoran el diseño de sistemas y la corrección automatizada, los cambios se pueden escalar en el entorno mediante el catálogo de servicios.
- **Mejora continua:** se pueden usar varias herramientas de supervisión para detectar mejoras incrementales que se pueden llevar a cabo en el siguiente paso del diseño, automatización y escalado del sistema.

### <a name="improve-system-design"></a>Mejora del diseño del sistema

La mejora del diseño del sistema es el enfoque más eficaz para mejorar las operaciones de cualquier plataforma común. Gracias a las mejoras en el diseño del sistema, la estabilidad puede aumentar y las interrupciones del negocio pueden disminuir. El diseño de sistemas individuales está fuera del ámbito de la perspectiva adoptada la vista en toda la plataforma de adopción de la nube. Como complemento de esta plataforma, el marco de arquitectura de Azure proporciona procedimientos recomendados para mejorar la resistencia y el diseño de un sistema específico. Estas mejoras de diseño se pueden aplicar al diseño de sistemas de una plataforma o carga de trabajo específicas.

El marco de arquitectura de Azure se centra en la mejora de cinco pilares del diseño de sistemas:

- **Escalabilidad:** escalado de los recursos comunes de la plataforma para controlar el aumento de la carga.
- **Disponibilidad:** disminución de las interrupciones empresariales al mejorar el tiempo de actividad potencial.
- **Resistencia:** mejora de los tiempos de recuperación para reducir la duración de las interrupciones.
- **Seguridad:** protección de las aplicaciones y datos frente a amenazas externas.
- **Administración:** procesos operativos específicos de los recursos comunes de la plataforma.

La mayoría de las interrupciones empresariales son resultado de alguna forma de deuda técnica o deficiencia en la arquitectura. En el caso de las implementaciones existentes, las mejoras en el diseño de los sistemas pueden verse como pagos de la deuda técnica existente. En el caso de las implementaciones nuevas, las mejoras en el diseño de los sistemas pueden verse como evasión de la deuda técnica. La siguiente sección, "Corrección automatizada", examina las formas de abordar la deuda técnica que no se puede o no se debe solucionar.

Obtenga más información acerca del [marco de arquitectura de Azure](https://docs.microsoft.com/azure/architecture/guide/pillars) para mejorar el diseño del sistema. A medida que el diseño del sistema mejora, vuelva a consultar este artículo para encontrar nuevas oportunidades de mejorar y escalar esas mejoras en todo el entorno.

### <a name="automated-remediation"></a>Corrección automatizada

Algunas deudas técnicas no se pueden (o no se deben) abordar, ya que la solución podría resultar demasiado costosa para corregirla. Esta se podría planear, pero es posible que tuviera una duración de proyecto excesiva. Podría deberse a que la interrupción del negocio no tiene un efecto importante en la empresa o a que la prioridad empresarial es recuperarse rápidamente en lugar de invertir en resistencia.

Cuando la ruta deseada no es la resolución de la deuda técnica, la corrección automática suele ser el siguiente paso deseado. El uso de Azure Automation y Azure Monitor para detectar tendencias y proporcionar una corrección automatizada es el enfoque más común para la corrección automatizada.

Para obtener instrucciones sobre la corrección automatizada, consulte [Azure Automation y alertas](https://docs.microsoft.com/azure/automation/automation-create-alert-triggered-runbook).

### <a name="scale-the-solution-with-a-service-catalog"></a>Escalado de la solución con un catálogo de servicios

La piedra angular de las operaciones de plataforma y la especialización de plataforma es un catálogo de servicios bien administrado. A través de él se escalan las mejoras en el diseño del sistema y las correcciones en un entorno. El equipo de plataforma en la nube y el equipo de automatización en la nube se coordinan para crear soluciones repetibles para las plataformas más comunes en cualquier entorno. Sin embargo, si esas soluciones no se aplican de forma coherente, la administración en la nube puede proporcionar poco más que una oferta de línea de base.

Para maximizar la adopción y minimizar la sobrecarga de mantenimiento de cualquier plataforma optimizada, dicha plataforma se debe agregar a un catálogo de servicios. Todas las aplicaciones del catálogo se pueden implementar para consumo interno a través del catálogo de servicios o como una oferta de Marketplace para consumidores externos.

Para más información sobre cómo publicar en un catálogo de servicios, consulte la serie de artículos sobre cómo [publicar en un catálogo de servicios](https://docs.microsoft.com/azure/managed-applications/publish-service-catalog-app).

### <a name="continuous-improvement"></a>Mejora continua

La especialización de la plataforma y las operaciones de la misma dependen de ciclos de comentarios sólidos entre los equipos de adopción, plataforma, automatización y administración. Si esos ciclos de comentarios están basados en datos, cada equipo puede tomar decisiones acertadas. En el caso de las operaciones de plataforma para lograr compromisos empresariales a largo plazo, es importante aprovechar la información específica de la plataforma centralizada. Dado que los contenedores y SQL Server son las dos plataformas administradas centralmente más habituales, los siguientes son algunos artículos que le ayudarán a empezar a usar la recopilación de datos para mejora continua.

- [Rendimiento de contenedores](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview)
- [Rendimiento de bases de datos PaaS](https://docs.microsoft.com/azure/azure-monitor/insights/azure-sql)
- [Rendimiento de bases de datos IaaS](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment)
