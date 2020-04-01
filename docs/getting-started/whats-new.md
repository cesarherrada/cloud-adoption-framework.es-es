---
title: Novedades
description: Más información sobre actualizaciones recientes en Microsoft Cloud Adoption Framework para Azure.
author: JanetCThomas
ms.author: janet
ms.date: 03/27/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: overview
ms.openlocfilehash: c701d49a80ea0ec087f26f792b7ffe8dbd4c061f
ms.sourcegitcommit: 1a4b140f09bdaa141037c54a4a3b5577cda269db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80392493"
---
<!-- markdownlint-disable MD024 -->

# <a name="whats-new-in-the-microsoft-cloud-adoption-framework-for-azure"></a>Novedades en Microsoft Cloud Adoption Framework para Azure

Esta es una lista de los cambios recientes realizados en Cloud Adoption Framework.

Este marco de trabajo se ha creado en colaboración con clientes, asociados y equipos internos de Microsoft. Se publica contenido nuevo y actualizado cuando está disponible. Estas versiones le permiten probar, validar y refinar la guía junto con nosotros. Le recomendamos que se asocie con nosotros en la creación del Cloud Adoption Framework para Azure.

## <a name="march-27-2020"></a>27 de marzo de 2020

Se han agregado instrucciones sobre las suscripciones iniciales que se deben crear al adoptar Azure.

### <a name="ready-updates"></a>Actualizaciones en la preparación

| Artículo                                                                                                                 | Descripción                                                                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Creación de las suscripciones de Azure iniciales](../ready/azure-best-practices/initial-subscriptions.md)                       | **Nuevo artículo:** cree las suscripciones de producción y de no producción iniciales, y decida si desea crear suscripciones de espacio aislado, así como una suscripción para que contenga servicios compartidos. |
| [Creación de suscripciones adicionales para escalar el entorno de Azure](../ready/azure-best-practices/scale-subscriptions.md) | Más información acerca de las razones para crear suscripciones adicionales, trasladar recursos entre suscripciones y sugerencias para crear nuevas suscripciones.                                                   |
| [Organización y administración de varias suscripciones de Azure](../ready/azure-best-practices/organize-subscriptions.md)             | Cree una jerarquía de grupos de administración que le ayude a organizar, administrar y gobernar las suscripciones de Azure.                                                                                         |

## <a name="march-20-2020"></a>20 de marzo de 2020

Hemos agregado instrucciones prescriptivas que incluyen las herramientas, los programas y el contenido clasificados por rol para impulsar la implementación correcta de aplicaciones en Kubernetes, desde la prueba de concepto a producción, seguida del escalado y la optimización.

### <a name="kubernetes"></a>Kubernetes

| Artículo                                                                                     | Descripción                                                                                                                                                                           |
|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Desarrollo e implementación de aplicaciones](../innovate/kubernetes/application-development.md) | **Nuevo artículo:** proporciona listas de comprobación, recursos y procedimientos recomendados para planear el desarrollo de aplicaciones, configurar canalizaciones de DevOps e implementar la ingeniería de confiabilidad de sitios para Kubernetes. |
| [Diseño y operaciones de clústeres](../innovate/kubernetes/cluster-design-operations.md) | **Nuevo artículo**: proporciona listas de comprobación, recursos y procedimientos recomendados para la configuración de clústeres, el diseño de red, la escalabilidad en el futuro, la continuidad empresarial y la recuperación ante desastres para Kubernetes. |
| [Seguridad de clústeres y aplicaciones](../innovate/kubernetes/cluster-application-security.md) | **Nuevo artículo:** proporciona listas de comprobación, recursos y procedimientos recomendados para el planeamiento de la seguridad, la producción y el escalado. |

## <a name="march-2-2020"></a>2 de marzo de 2020

En respuesta a los comentarios sobre la continuidad en el enfoque de migración en varias secciones de Cloud Adoption Framework entre las que se incluyen las fases de estrategia, planeamiento, preparación y migración, hemos realizado las siguientes actualizaciones. Estas actualizaciones están diseñadas para facilitar la comprensión de los ajustes de planeamiento y adopción a medida que continúa con el recorrido de migración.

### <a name="strategy-updates"></a>Actualizaciones de estrategia

| Artículo                                                                       | Descripción                                                                                                                                    |
|-------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| [Equilibrio de la cartera](../strategy/balance-the-portfolio.md)                 | Se ha hecho que este artículo aparezca antes en la metodología de estrategia. Esto le ofrece visibilidad sobre el proceso de reflexión anterior al ciclo de vida. |
| [Equilibrio&nbsp;entre prioridades&nbsp;contrapuestas](../strategy/balance-competing-priorities.md) | **Nuevo artículo:** describe el equilibrio de prioridades entre metodologías para ayudar a tomar decisiones con fundamento sobre su estrategia.                                         |

### <a name="plan-updates"></a>Actualizaciones en el planeamiento

| Artículo                                                             | Descripción                                                                                                                                                                           |
|---------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Procedimiento&nbsp;recomendado de&nbsp;evaluación](../plan/contoso-migration-assessment.md) | Este artículo se ha trasladado a la nueva sección "Procedimientos recomendados" de la metodología de planeamiento. Esto le proporciona visibilidad sobre el procedimiento de evaluación de entornos locales en una fase más temprana del ciclo de vida. |

### <a name="ready-updates"></a>Actualizaciones en la preparación

| Artículo                                                                   | Descripción                                                                                                              |
|---------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| [¿Qué&nbsp;es&nbsp;una&nbsp;zona de&nbsp;aterrizaje?](../ready/landing-zone/index.md)                 | **Nuevo artículo:** define el término zona de aterrizaje.                                                                          |
| [Primera zona de aterrizaje](../ready/landing-zone/first-landing-zone.md)         | **Nuevo artículo:** trata la comparación de diversas zonas de aterrizaje.                                                     |
| [Zona de aterrizaje de migración](../ready/landing-zone/migrate-landing-zone.md)     | Se ha separado la definición del plano técnico de Cloud Adoption Framework de la selección de la primera zona de aterrizaje.         |
| [Zona de aterrizaje de Terraform](../ready/landing-zone/terraform-landing-zone.md) | Se ha trasladado a la nueva sección "Zona de aterrizaje" de la metodología de preparación para elevar Terraform en el debate sobre la zona de aterrizaje. |

### <a name="migration-updates"></a>Actualizaciones en la migración

| Artículo                                                                                          | Descripción                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Información general](../migrate/azure-migration-guide/index.md)                                            | Se ha actualizado con una descripción más clara de la guía y con menos pasos.                                                                                                        |
| [Evaluar](../migrate/azure-migration-guide/assess.md)                                             | Se ha agregado la sección "Cuestionamiento de suposiciones", para demostrar cómo funciona este nivel de evaluación con el enfoque de evaluación incremental mencionado en la metodología de planeamiento. |
| [Clasificación durante los procesos de evaluación](../migrate/migration-considerations/assess/classify.md) | **Nuevo artículo:** describe la importancia de clasificar cada recurso y carga de trabajo antes de la migración.                                                                    |
| [Migrar](../migrate/azure-migration-guide/migrate.md)                                           | Se ha agregado una referencia a UnifyCloud en las opciones de herramientas de terceros en respuesta a los comentarios en las conferencias de nivel 1.                                                         |
| [Prueba,&nbsp;optimización&nbsp;y&nbsp;promoción](../migrate/azure-migration-guide/optimize-and-transform.md)        | Se ha alineado el título de este artículo con otras sugerencias de mejora de procesos.                                                                                           |
| [Introducción a la evaluación](../migrate/migration-considerations/assess/index.md)                           | Se ha actualizado para mostrar que la evaluación en esta fase se centra en la evaluación de la idoneidad técnica de una carga de trabajo específica y de los recursos relacionados.                               |
| [Lista de comprobación de planeamiento](../migrate/migration-considerations/prerequisites/planning-checklist.md)    | Se ha actualizado para aclarar la importancia de la alineación de las operaciones durante el planeamiento de los esfuerzos de migración y para garantizar una carga de trabajo bien administrada, posterior a la migración.                  |

<!-- test:ignoreNextStep -->
