---
title: Lista de comprobación del ámbito ampliado de la migración a la nube
description: Lista de comprobación del ámbito ampliado de la migración a la nube
author: BrianBlanchard
ms.author: brblanch
ms.date: 02/25/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 730da49f910c34bf2bd94b8766cb292520201e50
ms.sourcegitcommit: 58ea417a7df3318e3d1a76d3807cc4e7e3976f52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "78892640"
---
# <a name="expanded-scope-for-cloud-migration"></a>Ámbito ampliado para la migración a la nube

La [guía de migración a Azure](../azure-migration-guide/index.md) en Cloud Adoption Framework es el punto inicial sugerido para los lectores que estén interesados en una migración a Azure, también conocida como migración "lift and shift". Esta guía le guiará a través de una serie de requisitos previos, herramientas y enfoques para la migración de máquinas virtuales a la nube.

Si bien esta guía es una base de referencia eficaz para familiarizarse con este tipo de migración, hace varias suposiciones. Estos supuestos ofrecen un enfoque simplificado de las migraciones y hacen que la guía sea más accesible a muchos de los lectores de Cloud Adoption Framework. En esta sección de Cloud Adoption Framework se abordan algunos escenarios de migración de ámbito ampliado, que ayudan a guiar los esfuerzos cuando esos supuestos no se aplican.

## <a name="cloud-migration-expanded-scope-checklist"></a>Lista de comprobación del ámbito ampliado de la migración a la nube

En la siguiente lista de verificación se describen las áreas comunes de complejidad que podrían requerir que el ámbito de la migración se ampliara más allá de la [guía de migración a Azure](../azure-migration-guide/index.md).

### <a name="business-driven-scope-expansion"></a>Expansión del ámbito controlado por la empresa

- **[Apoyo de los mercados globales](../azure-best-practices/multiple-regions.md):** El negocio opera en varias regiones geográficas con diferentes requisitos de soberanía de datos. Para cumplir esos requisitos, deberían tenerse en cuenta consideraciones adicionales en el examen de los requisitos previos y la distribución de los recursos durante la migración.

### <a name="technology-driven-scope-expansion"></a>Expansión de ámbito controlado por la tecnología

- **[Migración de VMware](../azure-best-practices/vmware-host.md):** la migración de hosts de VMware puede acelerar el proceso de migración global. Todos los hosts de VMware migrados pueden mover varias cargas de trabajo a la nube con un enfoque de tipo "lift-and-shift". Después de la migración, esas máquinas virtuales y cargas de trabajo pueden permanecer en VMware o migrarse a las funcionalidades modernas de la nube.
- **[Migración de SQL Server](../azure-best-practices/sql-migration.md):** la migración de los servidores de SQL Server puede acelerar el proceso general de migración. Cada servidor de SQL Server migrado puede trasladar varias bases de datos y servicios, con lo que se acelerarían varias cargas de trabajo.
- **[Varios centros de datos](../azure-best-practices/multiple-datacenters.md):** la migración de varios centros de datos agrega una complejidad significativa. Durante los procesos de evaluación, migración, optimización y administración, se describen consideraciones adicionales para preparar entornos más complejos.
- **[Los requisitos de datos superan la capacidad de la red](../azure-best-practices/network-capacity-exceeded.md):** con frecuencia, las empresas optan por migrar a la nube porque la capacidad, la velocidad o la estabilidad de un centro de datos existente ya no son satisfactorias. Lamentablemente, esas mismas limitaciones agregan complejidad al proceso de migración y requieren un planeamiento adicional durante los procesos de evaluación y migración.
- **[Estrategia de cumplimiento o de gobernanza](../azure-best-practices/governance-or-compliance.md):** dado que la gobernanza y el cumplimiento son vitales para el éxito de una migración, es necesaria una alineación adicional entre los equipos de gobernanza de TI y el equipo de adopción de la nube.

Si alguna de estas complejidades está presente en su escenario, esta sección de Cloud Adoption Framework probablemente le proporcionará el tipo de guía que necesita para alinear adecuadamente el ámbito en los procesos de migración.

Cada uno de estos escenarios se aborda en los distintos artículos de esta sección de Cloud Adoption Framework.

## <a name="next-steps"></a>Pasos siguientes

Busque la tabla de contenido de la izquierda para abordar las necesidades específicas o los cambios en el ámbito. Además, la primera mejora del ámbito en la lista, [Compatibilidad con los mercados internacionales](../azure-best-practices/multiple-regions.md), es un buen punto de partida para revisar estos escenarios.

> [!div class="nextstepaction"]
> [Compatibilidad con los mercados internacionales](../azure-best-practices/multiple-regions.md)
