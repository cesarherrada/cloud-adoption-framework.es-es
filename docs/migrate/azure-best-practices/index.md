---
title: Procedimientos recomendados de migración de Azure
description: Use Cloud Adoption Framework para Azure para aprender a implementar las herramientas necesarias para realizar los procedimientos recomendados para la migración a la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: a7affd1d64e80cfdf85504ed62960de78a4a34a5
ms.sourcegitcommit: 88fbc36cd634c3069e1a841a763a5327c737aa84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80636363"
---
# <a name="best-practices-for-cloud-migration"></a>Procedimientos recomendados para la migración a la nube

Si está interesado en la migración a Azure, es aconsejable que la [guía de migración de Azure](../azure-migration-guide/index.md) de Cloud Adoption Framework sea su punto de partida. Esta guía le guiará a través de un conjunto de herramientas y enfoques básicos para la migración de máquinas virtuales a la nube. En esta sección de Cloud Adoption Framework se abordan muchos procedimientos recomendados que van más allá de las herramientas nativas de la nube básicas.

## <a name="cloud-migration-best-practices-checklist"></a>Lista de comprobación de procedimientos recomendados para la migración a la nube

En la siguiente lista de comprobación se describen las áreas comunes de complejidad que podrían requerir que el ámbito de la migración se ampliara más allá de la [guía de migración a Azure](../azure-migration-guide/index.md).

### <a name="business-driven-scope-expansion"></a>Expansión del ámbito controlado por la empresa

- **[Apoyo de los mercados globales](./multiple-regions.md):** El negocio opera en varias regiones geográficas con diferentes requisitos de soberanía de datos. Para cumplir esos requisitos, deberían tenerse en cuenta consideraciones adicionales en el examen de los requisitos previos y la distribución de los recursos durante la migración.

### <a name="technology-driven-scope-expansion"></a>Expansión de ámbito controlado por la tecnología

- **[Migración de VMware](./vmware-host.md):** la migración de hosts de VMware puede acelerar el proceso de migración global. Todos los hosts de VMware migrados pueden mover varias cargas de trabajo a la nube con un enfoque de tipo "lift-and-shift". Después de la migración, esas máquinas virtuales y cargas de trabajo pueden permanecer en VMware o migrarse a las funcionalidades modernas de la nube.
- **[Migración de SQL Server](./sql-migration.md):** la migración de los servidores de SQL Server puede acelerar el proceso general de migración. Cada servidor de SQL Server migrado puede trasladar varias bases de datos y servicios, con lo que se acelerarían varias cargas de trabajo.
- **[Varios centros de datos](./multiple-datacenters.md):** la migración de varios centros de datos agrega una complejidad significativa. Durante los procesos de evaluación, migración, optimización y administración, se describen consideraciones adicionales para preparar entornos más complejos.
- **[Los requisitos de datos superan la capacidad de la red](./network-capacity-exceeded.md):** con frecuencia, las empresas optan por migrar a la nube porque la capacidad, la velocidad o la estabilidad de un centro de datos existente ya no son satisfactorias. Lamentablemente, esas mismas limitaciones agregan complejidad al proceso de migración y requieren un planeamiento adicional durante los procesos de evaluación y migración.
- **[Estrategia de cumplimiento o de gobernanza](./governance-or-compliance.md):** dado que la gobernanza y el cumplimiento son vitales para el éxito de una migración, es necesaria una alineación adicional entre los equipos de gobernanza de TI y el equipo de adopción de la nube.

Si alguna de estas complejidades está presente en su escenario, esta sección de Cloud Adoption Framework probablemente le proporcionará el tipo de guía que necesita para alinear adecuadamente el ámbito en los procesos de migración.

Cada uno de estos escenarios se aborda en los distintos artículos de esta sección de Cloud Adoption Framework.

## <a name="next-steps"></a>Pasos siguientes

Busque la tabla de contenido de la izquierda para abordar las necesidades específicas o los cambios en el ámbito. Además, la primera mejora del ámbito en la lista, [Compatibilidad con los mercados internacionales](./multiple-regions.md), es un buen punto de partida para revisar estos escenarios.

> [!div class="nextstepaction"]
> [Compatibilidad con los mercados internacionales](./multiple-regions.md)
