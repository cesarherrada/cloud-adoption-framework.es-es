---
title: Consideraciones sobre la zona de aterrizaje de Azure
description: Conozca cómo una zona de aterrizaje proporciona el bloque de creación básico de cualquier entorno de adopción de la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 02/25/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 594f10968e45477895fcc5dcd1b2a95d16d7c861
ms.sourcegitcommit: 1a4b140f09bdaa141037c54a4a3b5577cda269db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80392649"
---
# <a name="first-landing-zone"></a>Primera zona de aterrizaje

La infraestructura como código es una transición natural durante la mayoría de los esfuerzos de adopción de la nube. La implementación de las primeras zonas de aterrizaje en la nube es un punto de partida común para realizar la transición a un entorno controlado por código. Este artículo le ayudará a comprender el término _zona de aterrizaje_ y a decidir qué zona de aterrizaje es la más adecuada para sus necesidades de adopción actuales.

## <a name="code-first-approach-to-landing-zones"></a>Enfoque code-first a las zonas de aterrizaje

En la imagen siguiente se muestran diversas opciones para las zonas de aterrizaje. Las siguientes opciones ayudan a seleccionar la zona de aterrizaje adecuada actual. También ayuda a establecer una visión para las necesidades futuras de zonas de aterrizaje.

![Opciones de la zona de aterrizaje](../../_images/ready/landing-zone-options.png)

A. Comience con código para generar zonas de aterrizaje coherentes y repetibles. Si se siente cómodo con la refactorización (o con el refinamiento del código y la infraestructura) a medida que aprende, empiece por un código base sencillo como el del plano técnico de la zona de aterrizaje de migración de Cloud Adoption Framework. Este enfoque acelera el éxito de la adopción y crea oportunidades prácticas de aprendizaje. Sin embargo, este tipo de zona de aterrizaje inicial no está diseñado para datos confidenciales o cargas de trabajo críticas, sin una refactorización adicional.

B. A medida que avanza la adopción y los requisitos se identifican más claramente, los equipos de adopción y de la plataforma refactorizarán las zonas de aprendizaje según lo que aprendieron. El proceso de expansión de las zonas de aterrizaje prepara los entornos para requisitos de cumplimiento o de arquitectura más complejos. La [expansión de la zona de aterrizaje](../considerations/index.md) proporciona guías de decisión y vínculos a procedimientos recomendados para guiar los esfuerzos de refactorización. La expansión de la zona de aterrizaje puede ayudar a cumplir con los requisitos de seguridad, operaciones y gobernanza.

C. Algunos planes de adopción de la nube están gobernados por requisitos de cumplimiento externos. Para reducir el esfuerzo que supone cumplir con estos requisitos, Azure proporciona varios ejemplos de planos técnicos de Azure. Algunos de ellos se pueden agregar al primer plano técnico inicial. Otros ejemplos incluyen también una implementación específica que puede servir como primera zona de aterrizaje.

D. Cuando un asociado proporciona servicios administrados continuos o se le contrata para cumplir el plan de adopción, este normalmente, proporcionará su propia zona de aterrizaje. El uso de una zona de aterrizaje de un asociado podría acelerar los esfuerzos de adopción y garantizar unos requisitos de administración operativa coherentes. No obstante, preste especial atención a los requisitos de gobernanza interna y seguridad para garantizar la alineación.

> [!NOTE]
> Antes de continuar con un enfoque basado primero en el código y centrado en refactorización, los lectores deben familiarizarse con las [prioridades en competencia tras esta decisión](../../strategy/balance-competing-priorities.md#balance-during-ready). Al elegir un enfoque de zona de aterrizaje, es importante comprender el equilibrio necesario entre "tiempo para adopción" y "operaciones a largo plazo".

## <a name="choosing-a-first-landing-zone"></a>Elección de una primera zona de aterrizaje

La selección de la primera zona de aterrizaje depende de un cierto número de variables. La siguiente cuadrícula captura algunas de las opciones para las primeras zonas de aterrizaje, junto con variables que pueden impulsar la decisión.

| Zona de aterrizaje                                 | Experiencia de la nube  | Escala             | Hora de detección | Listo para producción | Híbrido             | Información confidencial     | Crítica   | Cumplimiento normativo         |
|----------------------------------------------|-------------------|-------------------|----------------|------------------|--------------------|--------------------|--------------------|--------------------|
| [Migración de CAF](./migrate-landing-zone.md)     | Nuevo en la nube      | < 1000 recursos    | 1 a 5 días    | Ámbito limitado -> | Se requiere expansión | Se requiere expansión | Se requiere expansión | Se requiere expansión |
| [CAF Terraform](./terraform-landing-zone.md) | Varias plantillas | Varias plantillas | 10 a 20 semanas | Ámbito limitado -> | Módulos disponibles  | Módulos disponibles  | Módulos disponibles  | Módulos disponibles  |

La siguiente tabla muestra las mismas zonas de aterrizaje desde una perspectiva ligeramente diferente, para orientar procesos de decisiones más técnicas.

| Zona de aterrizaje                                 | Hub                          | Radio    | Modelo de nube | Technology      |
|----------------------------------------------|------------------------------|----------|-------------|-----------------|--|--|--|
| [Migración de CAF](./migrate-landing-zone.md)     | Se requiere refactorización            | Se incluye | Solo Azure  | Azure Blueprint |
| [CAF Terraform](./terraform-landing-zone.md) | Incluido en el módulo de VDC       | Se incluye | Nube múltiple  | Terraform       |

## <a name="next-steps"></a>Pasos siguientes

Si aún no está seguro de qué primera zona de aterrizaje elegir, le recomendamos que empiece con el [plano técnico de la zona de aterrizaje de migración de Cloud Adoption Framework](./migrate-landing-zone.md).

> [!div class="nextstepaction"]
> [Plano técnico de la zona de aterrizaje de migración de Cloud Adoption Framework](./migrate-landing-zone.md)
