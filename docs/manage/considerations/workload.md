---
title: 'Operaciones de la carga de trabajo: administración y operaciones de la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Operaciones de la carga de trabajo: administración y operaciones de la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 7eca93ba324a0e41f2a04e81a6bfe8994c232fcd
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73565043"
---
# <a name="workload-operations-in-cloud-management"></a>Operaciones de la carga de trabajo en la administración de la nube

Algunas cargas de trabajo son críticas para el éxito de la empresa. En el caso de esas cargas de trabajo, una base de referencia de administración no es suficiente para satisfacer los compromisos empresariales necesarios para la administración de la nube. Puede que incluso las operaciones de la plataforma no sean suficientes para satisfacer los compromisos empresariales. Este subconjunto de cargas de trabajo de gran importancia requiere un enfoque especializado en la forma en que funciona la carga de trabajo y cómo se respalda.

A cambio, la inversión en operaciones de la carga de trabajo puede conducir a mejoras en el rendimiento, un menor riesgo de interrupción del negocio y una recuperación más rápida cuando se producen errores del sistema. En este artículo se describe un enfoque para la inversión en las operaciones continuadas de estas cargas de trabajo de alta prioridad con el fin de favorecer mejores compromisos de negocio.

## <a name="when-to-invest-in-workload-operations"></a>Cuándo invertir en operaciones de la carga de trabajo

El _principio de Pareto_ (conocido también como la _regla 80/20_) afirma que el 80 % de los efectos proviene del 20 % de las causas. Cuando se permite que las carteras de TI crezcan de manera orgánica con el tiempo, esta regla se suele ilustrar en una revisión de la cartera de TI. En función del efecto que requiera la inversión, la causa puede variar, pero el principio general siempre se cumple:

- el 80 % de los errores del sistema suele ser el resultado del 20 % de los errores comunes.
- el 80 % del valor empresarial suele proceder del 20 % de las cargas de trabajo de una cartera.
- el 80 % del trabajo de migración a la nube proviene del 20 % de las cargas de trabajo que se mueven.
- el 80 % del trabajo de administración de la nube dará soporte al 20 % de los incidentes de servicio o incidencias de problemas.
- el 80 % del impacto en el negocio por una interrupción procederá del 20 % de los sistemas afectados por la interrupción.

Las operaciones de carga de trabajo solo se deben aplicar cuando haya una buena comprensión de la estrategia de adopción de la nube, los resultados empresariales y las métricas operativas. Se trata de un cambio de paradigma desde la visión clásica de la TI. Tradicionalmente, los responsables de TI dan por hecho que todas las cargas de trabajo han experimentado el mismo grado de asistencia y han requerido niveles de prioridad similares.

Antes de invertir en operaciones profundas de la carga de trabajo, tanto los responsables de TI como la empresa deben comprender las justificaciones empresariales y las expectativas del aumento de la inversión en la administración de la nube.

## <a name="start-with-the-data"></a>Comenzar con los datos

Las operaciones de la carga de trabajo comienzan con una profunda comprensión del rendimiento de la carga de trabajo y los requisitos de asistencia. Antes de invertir en operaciones de carga de trabajo, el equipo debe contar con datos completos sobre las dependencias de la carga de trabajo, el rendimiento de las aplicaciones, el diagnóstico de la base de datos, la telemetría de la máquina virtual y el historial de incidentes.

Estos datos son las simientes de los conocimientos que determinan las decisiones sobre las operaciones de la carga de trabajo.

## <a name="continued-observation"></a>Observación continua

Los datos iniciales y la telemetría continua pueden ayudar a formular y probar teorías sobre el rendimiento de una carga de trabajo. Sin embargo, las operaciones de carga de trabajo continuas proceden de una observación sistemática y ampliada del rendimiento de la carga de trabajo, con un gran énfasis en el rendimiento de los datos y las aplicaciones.

### <a name="test-the-automation"></a>Probar la automatización

En el nivel de aplicación, el primer requisito de las operaciones de la carga de trabajo es una inversión en pruebas en profundidad. En cualquier aplicación respaldada mediante operaciones de carga de trabajo, se debe establecer y ejecutar con regularidad un plan de prueba para ofrecer pruebas funcionales y de escala entre las aplicaciones.

La telemetría de prueba habitual puede proporcionar una validación inmediata de las diversas hipótesis sobre la operación de carga de trabajo. Se pueden ejecutar y probar patrones operativos y arquitectónicos de mejora. Las diferencias resultantes proporcionan un análisis de impacto claro para guiar las inversiones continuas.

### <a name="understand-releases"></a>Comprensión de las versiones

Comprender claramente los ciclos y las canalizaciones de versión es un elemento importante de las operaciones de carga de trabajo.

Una comprensión de los ciclos puede servir de preparación para posibles interrupciones y permitir que el equipo aborde de manera anticipada las versiones que pueden producir un efecto adverso en las operaciones. Asimismo, permite que el equipo de administración de la nube colabore con los equipos de adopción para mejorar continuamente la calidad del producto y solucionar errores que puedan afectar a la estabilidad.

Sobre todo, una comprensión de las canalizaciones de versión puede mejorar de manera considerable el objetivo de punto de recuperación (RPO) de una carga de trabajo. En muchos escenarios, el camino más rápido y preciso hacia la recuperación de una aplicación pasa por una canalización de versión. En el caso de las capas de aplicación que solo cambian cuando se produce una nueva versión, puede ser aconsejable invertir más en la optimización de la canalización que en la recuperación de la aplicación a partir de los procesos de copia de seguridad tradicionales.

Aunque una canalización de implementación puede ser el camino más rápido hacia la recuperación, también puede serlo hacia la corrección. Cuando una aplicación tiene una canalización de versión rápida, eficiente y confiable, el equipo de administración de la nube dispone de una opción para automatizar la implementación en un nuevo host como una forma de corrección automatizada.

Aunque puede haber otros muchos mecanismos más rápidos y eficaces de corrección y recuperación, cuando el uso de una canalización existente puede satisfacer los compromisos empresariales y rentabilizar las inversiones existentes en DevOps, la canalización existente puede ser una alternativa viable.

### <a name="clearly-communicate-changes-to-the-workload"></a>Comunicación clara de los cambios en la carga de trabajo

El cambio en cualquier carga de trabajo se encuentra entre los riesgos más importantes para las operaciones de la carga de trabajo. Para comprender los cambios que incluye cada versión, el equipo de administración de la nube debe estar estrechamente alineado con los equipos de adopción de la nube respecto a las cargas de trabajo que pertenecen al nivel de operaciones de la carga de trabajo de la administración de la nube. Esta inversión en conocimiento anticipado tendrá un impacto positivo directo sobre la estabilidad operativa.

## <a name="improve-outcomes"></a>Mejora de los resultados

Las inversiones en datos y comunicación de una carga de trabajo darán lugar a sugerencias de mejora para las operaciones en curso en una de las tres áreas siguientes:

- Resolución de deudas técnicas
- Corrección automatizada
- Mejora del diseño del sistema

### <a name="technical-debt-resolution"></a>Resolución de deudas técnicas

Los mejores planes de operaciones de carga de trabajo siguen necesitando correcciones. Dado que el equipo de administración de la nube busca permanecer conectado para comprender las versiones y el trabajo de adopción, igualmente debe compartir periódicamente los requisitos de corrección para garantizar que la deuda técnica y los errores sean una prioridad continua para los equipos de desarrollo.

### <a name="automated-remediation"></a>Corrección automatizada

Al aplicar el principio de Pareto, podemos decir que el 80 % del impacto empresarial negativo probablemente proviene del 20 % de los incidentes de servicio. Cuando esos incidentes no se pueden solucionar en los ciclos de desarrollo normales, las inversiones en la automatización de las correcciones pueden reducir considerablemente las interrupciones del negocio.

### <a name="improved-system-design"></a>Mejora del diseño del sistema

En los casos de resolución de deudas técnicas o automatización de correcciones, los defectos del sistema son la causa común de la mayoría de las interrupciones del sistema. La adhesión a unos pocos principios de diseño puede tener el impacto más grande en las operaciones generales de carga de trabajo:

- **Escalabilidad:** La capacidad de un sistema para controlar el aumento de la carga.
- **Disponibilidad:** proporción de tiempo que un sistema es funcional y está en funcionamiento.
- **Resistencia:** La capacidad de un sistema de recuperarse de los errores y seguir funcionando.
- **Administración:** Procesos de operaciones que mantienen un sistema ejecutándose en producción.
- **Seguridad:** Protección de las aplicaciones y los datos frente a amenazas.

Para ayudar a mejorar las operaciones generales, el [marco de arquitectura de Azure](https://docs.microsoft.com/azure/architecture/guide/pillars) proporciona un enfoque para evaluar cargas de trabajo específicas para el cumplimiento de estos fundamentos. Estos fundamentos se pueden aplicar tanto a las operaciones de la plataforma como a las de la carga de trabajo.

## <a name="next-steps"></a>Pasos siguientes

Con un conocimiento completo de la metodología de administración dentro de Cloud Adoption Framework, ahora está preparado para implementar los principios de administración de la nube. Para obtener una guía sobre cómo convertir esta metodología en accionable en su entorno de operaciones, consulte el apartado [Administración de la nube en Cloud Adoption Framework](../index.md) del ciclo de vida de adopción.

> [!div class="nextstepaction"]
> [Aplicación de esta metodología](../index.md)
