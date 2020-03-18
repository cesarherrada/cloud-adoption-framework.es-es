---
title: Novedades
description: Más información sobre las actualizaciones en Microsoft Cloud Adoption Framework para Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 03/02/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: reference
ms.openlocfilehash: 0e93f0279ba210be594b3b5af40cf16657f224e3
ms.sourcegitcommit: 959cb0f63e4fe2d01fec2b820b8237e98599d14f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "79095384"
---
# <a name="whats-new-in-the-microsoft-cloud-adoption-framework"></a>Novedades en Microsoft Cloud Adoption Framework

## <a name="fulfilling-the-vision"></a>Cumplimiento de la visión

El marco ha alcanzado la disponibilidad general (GA). Sin embargo, vamos a crear activamente este marco en colaboración con clientes, asociados y equipos internos. Para fomentar la cooperación, el contenido se publica a medida que está disponible. Estas versiones públicas permiten probar, validar y perfeccionar la guía por fases.

Los cambios importantes se capturan en las siguientes notas de la versión.

## <a name="migration-update-03022020"></a>Actualización de la migración: 02/03/2020

Esta versión respondió a los comentarios relacionados con la continuidad del enfoque de migración mediante varias metodologías, incluidas las de estrategia, plan, preparado y migración. El objetivo de esta versión era ayudar a que los lectores comprendiesen el perfeccionamiento continuado del planeamiento y la adopción, a medida que los clientes continúan el recorrido de la migración. Se realizaron los siguientes cambios para cumplir el espíritu de esta versión:

### <a name="new-articles"></a>Artículos nuevos

- [Equilibrio de prioridades en la competencia](../strategy/balance-competing-priorities.md): describe el equilibrio de prioridades que se produce en cada metodología para informar de las estrategias de los clientes.
- [Clasificación durante los procesos de evaluación](../migrate/migration-considerations/assess/classify.md): describe la importancia de clasificar cada recurso y carga de trabajo antes de la migración.

### <a name="restructure-landing-zone-process"></a>Reestructuración del proceso de la zona de aterrizaje

La primera zona de aterrizaje se ha extraído de la guía de preparación para contar con su propia sección. Este enfoque nos permite ampliar el concepto de zonas de aterrizaje y opciones de zona de aterrizaje. Esto también llevó a la creación de algunos artículos nuevos:

- [¿Qué es una zona de aterrizaje?](../ready/landing-zone/index.md): define el término zona de aterrizaje.
- [Primera zona de aterrizaje](../ready/landing-zone/first-landing-zone.md): trata la comparación de diversas zonas de aterrizaje.
- [Zona de aterrizaje de migración](../ready/landing-zone/migrate-landing-zone.md): se ha movido el artículo de plano técnico de la zona de aterrizaje anterior, para separar la definición del plano técnico de CAF de la selección de la primera zona de aterrizaje y así permitir más opciones de zona de aterrizaje.
- Artículo sobre [zonas de aterrizaje de Terraform](../ready/landing-zone/terraform-landing-zone.md): se ha movido de la sección "Ámbito ampliado" de la metodología Preparado a la nueva sección "Zona de aterrizaje" de la metodología Preparado, para tratar a Terraform como elemento principal en el cuestión de la zona de aterrizaje.
- En la tabla de contenido se han agrupado bajo "Consideraciones básicas sobre la zona de aterrizaje" este tipo de consideraciones.
- Se han trasladado los procedimientos recomendados de seguridad desde la metodología Migrar a una nueva sección de zona de aterrizaje "Mejora de la seguridad de la zona de aterrizaje (información confidencial)", para que los lectores vean esta guía en una fase más temprana del ciclo de vida.

### <a name="refinements-to-the-azure-migration-guide"></a>Ajustes en la guía de migración a Azure

Los patrones de tráfico de los usuarios sugieren que es más probable que esta sección de contenido la usen los implementadores y arquitectos durante su primera migración. Para ofrecer un mejor servicio a este público, se ha adaptado el enfoque de la guía de migración con el fin de adaptarse mejor a la intención original de mostrar a los lectores las herramientas que se usan durante la primera migración.

- [Información general](../migrate/azure-migration-guide/index.md): descripción más clara de la guía, con un menor número de pasos.
- [Evaluación](../migrate/azure-migration-guide/assess.md): ilustra mejor que la evaluación en esta fase se centra en la evaluación de la idoneidad técnica de una carga de trabajo específica y de los recursos relacionados. Se ha agregado la sección Cuestionamiento de suposiciones, para demostrar cómo funciona este nivel de evaluación con el enfoque de evaluación incremental mencionado por primera vez en la metodología de plan.
- [Migración](../migrate/azure-migration-guide/migrate.md): en respuesta a los comentarios en las conferencias de nivel 1, se ha agregado una referencia a UnifyCloud en las opciones de herramientas de terceros.
- [Prueba, optimización y promoción](../migrate/azure-migration-guide/optimize-and-transform.md): se ha alineado el título de este artículo con otras sugerencias para mejorar el proceso.

### <a name="refinements-to-migration-process-improvements"></a>Ajustes en las mejoras en el proceso de migración

- [Introducción a la evaluación](../migrate/migration-considerations/assess/index.md): ilustra mejor que la evaluación en esta fase se centra en la evaluación de la idoneidad técnica de una carga de trabajo específica y de los recursos relacionados.
- [Lista de comprobación del planeamiento](../migrate/migration-considerations/prerequisites/planning-checklist.md): aclara la importancia de la alineación de las operaciones durante el planeamiento de los esfuerzos de migración, para garantizar una carga de trabajo bien administrada, posterior a la migración.

### <a name="placement-of-related-articles"></a>Ubicación de artículos relacionados

Cada artículo indicado a continuación se ha movido. El tráfico redirige a la nueva ubicación.

- Artículo sobre el [procedimiento recomendado de evaluación](../plan/contoso-migration-assessment.md): se ha trasladado de la sección "Procedimientos recomendados" de la metodología de migración a la nueva sección "Procedimientos recomendados" de la metodología de plan. Este movimiento muestra a los lectores la práctica de evaluación de entornos locales en una fase más temprana del ciclo de vida.
- Artículo [Conciliar la cartera](../strategy/balance-the-portfolio.md): se ha trasladado de la sección "Ámbito ampliado" de la metodología de migración a la metodología de estrategia. Este movimiento muestra a los lectores este proceso de pensamiento en una fase más temprana del ciclo de vida.

### <a name="alignment-of-the-changes"></a>Alineación de los cambios

- [Introducción a la preparación](../ready/index.md): se han actualizado los cuatro pasos de la introducción sobre la preparación para reflejar el proceso mejorado.
- [Introducción a la migración](../migrate/index.md): se han actualizado los pasos de la introducción sobre la migración para reflejar el proceso mejorado.
- [Gráfico de la metodología de migración](../migrate/index.md): se ha actualizado la imagen de la metodología para reflejar los cambios.
- [Gráfico de introducción](../index.md): se ha actualizado el gráfico de introducción para reflejar los cambios.
