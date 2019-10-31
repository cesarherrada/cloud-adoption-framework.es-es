---
title: 'Inventario y visibilidad: administración y operaciones en la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Inventario y visibilidad: administración y operaciones en la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: f5a2b84fead3adef17767f99d4079ac54fb421ea
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683619"
---
# <a name="inventory-and-visibility-in-cloud-management"></a>Inventario y visibilidad de la administración en la nube

La administración operativa depende claramente de los datos. Una administración coherente requiere un conocimiento claro de lo que se administra (inventario) y de cómo cambian los recursos y las cargas de trabajo administrados con el tiempo (visibilidad). En conjunto, la claridad y la visibilidad del inventario permiten al equipo administrar el entorno de forma eficaz. Todas las demás actividades y procesos de administración operativa se basan en estas dos áreas de información.

Algunas frases clásicas sobre la importancia de las medidas establecen la línea de este artículo: Administrar lo que importa. Solo se puede administrar lo que se puede medir. Si no se puede medir, es posible que no sea importante. La materia de inventario y visibilidad se basa en estas frases atemporales. Antes de establecer los procesos de administración operativa, es importante recopilar datos y crear el nivel adecuado de visibilidad para los equipos correctos.

## <a name="common-customer-challenges"></a>Desafíos comunes de los clientes

Cuando los procesos de inventario y visibilidad no se aplican de forma coherente, los equipos de administración operativa sufren un mayor volumen de interrupciones del negocio, tiempos de recuperación más prolongados y mayor esfuerzo necesario para solucionar y evaluar los problemas. Cuando los cambios afectan a aplicaciones de mayor prioridad y a un gran número de recursos, cada una de estas métricas crece aún más rápido.

Estos desafíos derivan de un pequeño número de preguntas que solo se pueden responder mediante datos y telemetría coherentes:

- ¿En qué medida se desvía el rendimiento actual de los datos de telemetría de rendimiento operativos estándar?
- ¿Qué recursos están causando las interrupciones del negocio en el nivel de carga de trabajo?
- ¿Qué recursos deben corregirse para volver al rendimiento aceptable de este proceso de negocio o carga de trabajo?
- ¿Cuándo se inició la desviación? ¿Cuál fue el desencadenador?
- ¿Qué cambios se han realizado en los recursos subyacentes? ¿Quién los ha realizado?
- ¿Los cambios son intencionados? ¿Malintencionados?
- ¿Cómo afectan los cambios a los datos de telemetría del rendimiento?

Es difícil, si no imposible, responder a estas preguntas sin un origen enriquecido y centralizado de registros y datos de telemetría. Para habilitar la administración en la nube, el servicio de línea de base debe empezar por definir los procesos para garantizar una configuración coherente, necesaria para centralizar los datos. Estos procesos capturarán cómo la configuración aplica la recopilación de datos para poder contar con los componentes de inventario y visibilidad en la sección siguiente.

## <a name="components-of-inventory-and-visibility"></a>Componentes de inventario y visibilidad

La creación de visibilidad en cualquier plataforma de nube requiere algunos componentes clave:

1. Responsabilidad y visibilidad
2. Inventario
3. Registro central
4. Seguimiento de cambios
5. Telemetría de rendimiento

### <a name="responsibility-and-visibility"></a>Responsabilidad y visibilidad

A la hora de establecer compromisos para cada carga de trabajo, la [responsabilidad de la administración](./commitment.md#management-responsibility) es un factor clave. La responsabilidad delegada crea una necesidad de visibilidad delegada. El primer paso hacia el inventario y la visibilidad es asegurarse de que las partes interesadas tengan acceso a los datos correctos. Antes de implementar las herramientas en la nube nativas para la visibilidad, asegúrese de que cada herramienta de supervisión se ha configurado con el acceso y el ámbito adecuados para cada equipo de operaciones.

### <a name="inventory"></a>Inventario

Si nadie sabe que existe un recurso, es muy difícil que se administre. Para poder administrar un recurso o una carga de trabajo, deben inventariarse y clasificarse. El primer paso técnico hacia la estabilidad de las operaciones es validar y clasificar el inventario.

### <a name="central-logging"></a>Registro central

Tener un registro central es fundamental para dar a los equipos de administración la visibilidad que necesitan sobre las operaciones diarias. Todos los recursos implementados en la nube deben guardar los registros en una ubicación central. En Azure, la ubicación central es Log Analytics. La centralización de los registros permite crear informes sobre la administración de cambios, el estado de mantenimiento del servicio, la configuración y muchos otros aspectos de las operaciones de TI.

Realizar un uso coherente del registro central es el primer paso hacia operaciones repetibles coherentes. La aplicación se puede realizar mediante directivas corporativas. Sin embargo, cuando sea posible, la aplicación se debe automatizar para garantizar la coherencia.

### <a name="change-tracking"></a>Seguimiento de cambios

Los cambios son una constante en los entornos tecnológicos. Conocer y comprender los cambios en las distintas cargas de trabajo es esencial para contar con operaciones confiables. Cualquier solución de administración en la nube debe incluir un medio para comprender el cuándo, cómo y por qué de un cambio técnico. Sin esos datos, las labores de corrección resultan mucho más difíciles.

### <a name="performance-telemetry"></a>Telemetría de rendimiento

Los compromisos empresariales con respecto a la administración en la nube se controlan mediante datos. Para mantener los compromisos correctamente, el equipo de operaciones en la nube debe comprender primero los datos de telemetría en cuanto a estabilidad, rendimiento y operaciones de la carga de trabajo, así como los recursos que respaldan la carga de trabajo.

Las operaciones y el mantenimiento continuos de la red, servidores DNS, sistemas operativos y otros aspectos fundamentales del entorno son puntos de datos críticos que afectan al estado general de cualquier carga de trabajo.

## <a name="processes"></a>Procesos

Quizás más importante que las características de la plataforma de administración en la nube son los procesos de administración en la nube, que se encargarán de los compromisos de operaciones con la empresa. Cualquier metodología de administración en la nube debe incluir, como mínimo, los siguientes procesos:

- Supervisión reactiva: cuando las desviaciones afectan a las operaciones empresariales, ¿quién aborda esas desviaciones? ¿Qué acciones llevan a cabo para corregir las desviaciones?
- Supervisión activa: cuando se detectan desviaciones pero las operaciones empresariales no se ven afectadas, ¿cómo se abordan esas desviaciones y quién lo hace?
- Informes de compromiso: ¿Cómo se comunica el cumplimiento del compromiso confirmado por la empresa a las partes interesadas del negocio?
- Revisiones presupuestarias: ¿Cuál es el proceso de revisión de dichos compromisos con relación a los costos presupuestados? ¿Cuál es el proceso de ajuste de la solución implementada o de los compromisos para crear la alineación?
- Rutas de escalación: ¿Qué rutas de escalación hay disponibles cuando alguno de los procesos anteriores no satisface las necesidades del negocio?

Hay varios procesos más relacionados con el inventario y la visibilidad. La lista anterior está diseñada para generar ideas en el equipo de operaciones. Al responder a estas preguntas, surgirán algunos de los procesos necesarios. Lo más probable es que también desencadene nuevas preguntas más profundas.

## <a name="responsibilities"></a>Responsabilidades

Al desarrollar procesos de supervisión de las operaciones, es igualmente importante determinar las responsabilidades de soporte regular y de las operaciones diarias para cada proceso.

En una organización de TI central, el departamento de TI proporcionaría la experiencia operativa. La empresa tendría una naturaleza consultiva a la hora de corregir los problemas.
En la organización de un centro de excelencia en la nube, las operaciones empresariales proporcionarían la experiencia y serían responsables de la administración de estos procesos. El departamento de TI se centraría en la automatización y la prestación de soporte a los equipos, ya que operan en el entorno.

Sin embargo, estas son las responsabilidades comunes. A menudo, las organizaciones requieren una combinación de responsabilidades para satisfacer los compromisos del negocio.

## <a name="acting-on-inventory-and-visibility"></a>Actuación en el inventario y la visibilidad

Independientemente de la plataforma de nube, los cinco componentes de inventario y visibilidad se usan en la mayoría de los procesos operativos. Todas las materias posteriores se basarán en los datos que se van a capturar. En los siguientes artículos de esta serie se describen las formas de actuar sobre esos datos y cómo integrar otros orígenes de datos.

### <a name="sharing-visibility"></a>Visibilidad compartida

Los datos sin acción no producen retornos. La administración en la nube puede expandirse más allá de los procesos y las herramientas nativas de la nube. Para dar cabida a procesos más amplios, es posible que sea necesario mejorar la línea de base de administración en la nube para que incluya informes, integración de la administración de servicios de TI o centralización de los datos. Es posible que la administración en la nube necesite incluir una o varias de las siguientes operaciones durante las distintas fases de madurez operativa.

### <a name="reporting"></a>Informes

Los procesos sin conexión y la comunicación de los compromisos a las partes interesadas del negocio suelen requerir informes. Un autoservicio de informes o los informes periódicos pueden ser un componente necesario de una línea de base de administración mejorada.

### <a name="it-service-management-itsm-integration"></a>Integración de administración de servicios de TI (ITSM)

La integración de ITSM suele ser el primer ejemplo de la actuación en el inventario y la visibilidad. Cuando surgen desviaciones de los patrones de rendimiento esperados, la integración de ITSM usará las alertas de la plataforma de nube para abrir incidencias en una herramienta de administración de servicios independiente con el fin de iniciar las actividades de corrección. Algunos modelos operativos pueden requerir la integración de ITSM como un aspecto de la línea de base de administración mejorada.

### <a name="data-centralization"></a>Centralización de los datos

Hay varias razones por las que un negocio puede necesitar varios inquilinos dentro de un único proveedor de nube. En estos escenarios, la centralización de los datos es un componente necesario de la línea base de administración mejorada para proporcionar visibilidad en cada uno de esos inquilinos o entornos.

## <a name="next-steps"></a>Pasos siguientes

El cumplimiento operativo se basa en las funcionalidades de inventario y en la aplicación de controles y automatización de la administración. Consulte la correspondencia entre el [cumplimiento operativo](./operational-compliance.md) y sus procesos.

> [!div class="nextstepaction"]
> [Plan de cumplimiento operativo](./operational-compliance.md)
