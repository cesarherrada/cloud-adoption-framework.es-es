---
title: ¿Qué es una zona de aterrizaje?
description: Conozca cómo una zona de aterrizaje proporciona el bloque de creación básico de cualquier entorno de adopción de la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 02/25/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 907cb23b61ffada1a97abe87545ed7d4cdd7d56a
ms.sourcegitcommit: 1a4b140f09bdaa141037c54a4a3b5577cda269db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80392587"
---
<!-- markdownlint-disable MD026 -->

# <a name="what-is-a-landing-zone"></a>¿Qué es una zona de aterrizaje?

La infraestructura como código es una transición natural durante la mayoría de los esfuerzos de adopción de la nube. La implementación de las primeras zonas de aterrizaje en la nube es un punto de partida común para realizar la transición a la creación del entorno de Code First. Este artículo le ayudará a comprender el término _zona de aterrizaje_ y otros términos relacionados.

## <a name="landing-zone-definition"></a>Definición de zona de aterrizaje

Una zona de aterrizaje es el bloque de creación básico de cualquier entorno de adopción de la nube. El término _zona de aterrizaje_ hace referencia a una construcción lógica que captura todo lo que se debe dar para posibilitar la adopción de la nube deseada.

**Ámbito:** una zona de aterrizaje completamente funcional analiza todos los recursos de la plataforma que son necesarios para admitir las necesidades de adopción del cliente.

**Refactorización:** una zona de aterrizaje plenamente funcional es el resultado final de cualquier iteración de la metodología de preparación de Cloud Adoption Framework. Durante cada iteración, el código base que define la zona de aterrizaje se refactoriza o expande. Después de la refactorización, la zona de aterrizaje se puede modificar o volver a implementar para permitir nuevas necesidades de adopción de la nube.

**Objetivo:** el objetivo del enfoque con zona de aterrizaje es crear un conjunto común de implementaciones de plataforma coherentes. Estas implementaciones coherentes deben estar en vigor para garantizar que las aplicaciones tendrán acceso a los componentes necesarios cuando se implementen. Por consiguiente, cada iteración de zona de aterrizaje debe diseñarse e implementarse de acuerdo con los requisitos del plan de adopción de la nube y la estrategia de diseño de la suscripción.

**Propósito principal:** El propósito principal de la zona de aterrizaje es garantizar que, cuando una aplicación aterriza en Azure, ya existen los recursos necesarios.

## <a name="landing-zone-usage"></a>Uso de la zona de aterrizaje

Las zonas de aterrizaje no distinguen necesariamente entre la adopción de IaaS o PaaS. Sin embargo, las zonas de aterrizaje están creadas específicamente para respaldar el plan de adopción mediante el cumplimiento de la estrategia de suscripción. Respaldar el plan de adopción puede requerir varias zonas de aterrizaje con una mezcla de los componentes necesarios.

El propósito y el ámbito del plan general de adopción de la nube definirá qué recursos son necesarios. Probablemente se agregarán requisitos adicionales de gobernanza, cumplimiento, seguridad y administración operativa al ámbito inicial de la zona de aterrizaje. Durante las primeras fases de adopción, las zonas de aterrizaje pueden incluir menos recursos a causa de los requisitos definidos y los riesgos aceptables.  Cuando existen varias zonas de aterrizaje, es muy común que cada zona de aterrizaje dependa de los centros de conectividad que proporcionan los controles necesarios mediante un modelo de servicio compartido.

## <a name="related-terms"></a>Términos relacionados

- **Servicios compartidos:** Las cargas de trabajo suelen tener dependencias compartidas utilizadas por muchas cargas de trabajo diferentes. El enfoque de servicios compartidos mueve muchas de esas dependencias comunes a una construcción lógica.

- **Modelo en estrella tipo hub-and-spoke:** Una implementación del enfoque de servicios compartidos es un modelo en estrella tipo hub-and-spoke. En este modelo, el centro de conectividad es la única construcción lógica para hospedar todos los servicios compartidos. Las zonas de aterrizaje actúan como radios que irradian fuera del centro de conectividad, según las dependencias comunes.

- **Zona de aterrizaje independiente:** Algunos enfoques de las zonas de aterrizaje no llaman específicamente a un centro de conectividad dedicado. Esto se suele ver habitualmente cuando todos los recursos de producción (aplicaciones, datos y máquinas virtuales) del plan de adopción de la nube se pueden hospedar, administrar y gobernar de forma segura en un solo entorno.

## <a name="next-steps"></a>Pasos siguientes

Para empezar a usar zonas de aterrizaje, [elija su primera zona de aterrizaje](./first-landing-zone.md).

> [!div class="nextstepaction"]
> [Elección de la primera zona de aterrizaje](./first-landing-zone.md)
