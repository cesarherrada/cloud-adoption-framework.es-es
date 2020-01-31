---
title: 'Preparación para la complejidad cultural: alineación de roles y responsabilidades'
description: Preparación para la complejidad cultural mediante la alineación de roles y responsabilidades
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 186772796694d6ef60a923c5098760a573d8db6d
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76801501"
---
# <a name="prepare-for-cultural-complexity-aligning-roles-and-responsibilities"></a>Preparación para la complejidad cultural: alineación de roles y responsabilidades

Es importante comprender la referencia cultural necesaria para poner en funcionamiento los centros de recursos existentes para que cualquier migración se realice correctamente. En algunas organizaciones, la administración de los centros de datos está incluida en los equipos de operaciones de TI centralizados. En estos equipos centralizados, los roles y las responsabilidades tienden a estar bien definidos y a que todo el equipo los comprenda bien. En el caso de las empresas más grandes, especialmente las que están determinadas por los requisitos de cumplimiento normativo de terceros, la referencia cultural tiende a ser más matizada y compleja. La complejidad cultural puede llevar a obstáculos que son difíciles de comprender y que tardan mucho tiempo en superarse.

En cualquier escenario, es recomendable invertir en la documentación de los roles y las responsabilidades que se necesitan para completar una migración. En este artículo se describen algunos de los roles y las responsabilidades que se han visto en una migración de centros de datos, para servir como plantilla para la documentación que puede brindar claridad a lo largo de la ejecución.

## <a name="business-functions"></a>Funciones empresariales

En cualquier migración, hay algunas funciones clave que las ejecuta mejor en la empresa, siempre que sea posible. A menudo, el departamento de TI es capaz de completar las tareas siguientes. Sin embargo, la participación de miembros de la empresa podría ayudar a disminuir las barreras más adelante en el proceso de adopción. También garantiza la inversión mutua de las partes interesadas clave durante todo el proceso de migración.

| Proceso | Actividad | Descripción |
|---------|---------|---------|
| Evaluar | Objetivos empresariales | Definir los resultados empresariales deseados del esfuerzo de migración. |
| Evaluar | Prioridades | Garantizar la alineación con las cambiantes necesidades del negocio y las condiciones del mercado. |
| Evaluar | Justificación | Validar las suposiciones que impulsan las justificaciones comerciales que están en constante evolución. |
| Evaluar | Riesgo | Ayudar al equipo de adopción de la nube a comprender el impacto de los riesgos empresariales tangibles. |
| Evaluar | Aprobación | Revisar y aprobar el impacto en la empresa de los cambios de arquitectura propuestos. |
| Optimización | Plan de cambio | Definir un plan para el consumo de cambios dentro de la empresa, incluidos los períodos de baja actividad y los bloqueos de cambio. |
| Optimización | Prueba | Alinear a los usuarios avanzados capaces de validar el rendimiento y la funcionalidad. |
| Proteger y administrar | Impacto de la interrupción | Ayudar al equipo de adopción de la nube a cuantificar el impacto de una interrupción del proceso de negocio. |
| Proteger y administrar | Validación del acuerdo de nivel de servicio | Ayudar al equipo de adopción de la nube a definir acuerdos de nivel de servicio y las tolerancias aceptables para interrupciones del negocio. |

En última instancia, el equipo de adopción de la nube es responsable de cada una de estas actividades. Sin embargo, el establecimiento de responsabilidades y una cadencia periódica con el negocio para completar estas actividades a un ritmo establecido puede mejorar la alineación y la cohesión de las partes interesadas con el negocio.

## <a name="common-roles-and-responsibilities"></a>Roles y responsabilidades comunes

Cada proceso dentro de la descripción de los principios de migración de la Plataforma de adopción de la nube incluye un artículo de proceso en el que se describen actividades específicas para alinear los roles y las responsabilidades. Para mayor claridad durante la ejecución, se debe asignar una sola entidad responsable para cada actividad, junto con cualquier otra parte responsable necesaria para admitir dichas actividades. Sin embargo, la lista siguiente contiene una serie de roles y responsabilidades comunes que tienen un mayor grado de impacto en la ejecución de la migración. Estos roles se deben identificar en una fase temprana del esfuerzo de migración.

> [!NOTE]
> En la tabla siguiente, una entidad responsable debe iniciar la alineación de los roles. Esa columna se debe personalizar para ajustarse a los procesos existentes para realizar una ejecución eficaz. Idealmente, se debe designar una sola persona como la entidad responsable.

| Proceso | Actividad | Descripción | Entidad responsable |
|---------|---------|---------|---------|
| Requisito previo | Patrimonio digital | Alinear el inventario existente con los supuestos básicos, en función de los resultados empresariales. | Equipo de estrategia en la nube |
| Requisito previo | Trabajo pendiente de migración | Clasificar por orden de prioridad la secuencia de cargas de trabajo que quiere migrar. | Equipo de estrategia en la nube |
| Evaluar | Architecture | Desafiar las suposiciones iniciales para definir la arquitectura de destino en función de las métricas de uso. | Equipo de adopción de la nube |
| Evaluar | Aprobación | Aprobar la arquitectura propuesta. | Equipo de estrategia en la nube |
| Migrar | Acceso de replicación | Acceder a los hosts locales existentes y a los recursos para establecer procesos de replicación. | Equipo de adopción de la nube |
| Optimización | Ready | Comprobar que el sistema cumple los requisitos de rendimiento y costo antes de la promoción. | Equipo de adopción de la nube |
| Optimización | Promoción | Permisos para promover una carga de trabajo a producción y redirigir el tráfico de producción. | Equipo de adopción de la nube |
| Proteger y administrar | Transición de operaciones | Documentar los sistemas de producción antes de las operaciones de producción. | Equipo de adopción de la nube |

> [!CAUTION]
> Para estas actividades, los permisos y las autorizaciones influyen en gran medida en la parte responsable, que debe tener acceso directo a los sistemas de producción en el entorno existente o debe tener medios para proteger el acceso a través de otros actores responsables. Determinar esta entidad responsable afecta directamente a la estrategia de promoción durante el proceso de migración y optimización.

## <a name="next-steps"></a>Pasos siguientes

Cuando el equipo entiende en términos generales los roles y las responsabilidades, es el momento de empezar a preparar los detalles técnicos de la migración. Comprender [la complejidad técnica y la administración de cambios](./technical-complexity.md) puede ayudarlo a preparar el equipo de adopción de la nube para la complejidad técnica de la migración mediante la alineación con un proceso de administración de cambios incremental.

> [!div class="nextstepaction"]
> [Complejidad técnica y administración de cambios](./technical-complexity.md)
