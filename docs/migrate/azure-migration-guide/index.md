---
title: Introducción a la guía de migración a Azure
description: Use Cloud Adoption Framework para Azure para aprender a migrar de manera eficaz los servicios de la organización a Azure.
author: matticusau
ms.author: mlavery
ms.date: 02/25/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.custom: fasttrack-new, AQC
ms.localizationpriority: high
ms.openlocfilehash: 4ef888e26089a2262fadeb93ec33ed063bcbf753
ms.sourcegitcommit: 88fbc36cd634c3069e1a841a763a5327c737aa84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80636505"
---
# <a name="azure-migration-guide-before-you-start"></a>Guía de migración a Azure: Antes de comenzar

La [Metodología de migración de Cloud Adoption Framework](../index.md) guía a los lectores a través de un proceso iterativo de migración de una carga de trabajo, o de una pequeña colección de cargas de trabajo por cada lanzamiento. En cada iteración, se sigue el proceso de evaluación, migración, optimización y promoción para asegurarse de que las cargas de trabajo están listas para satisfacer las demandas de producción. Ese proceso independiente de la nube puede guiar la migración a cualquier proveedor de servicios en la nube.

En esta guía se muestra una versión simplificada de ese proceso cuando migra desde su entorno local a **Azure**.

::: zone target="docs"

> [!TIP]
> Para una experiencia interactiva, consulte esta guía en Azure Portal. Vaya al [Centro de inicio rápido de Azure](https://portal.azure.com/?feature.quickstart=true#blade/Microsoft_Azure_Resources/QuickstartCenterBlade) en Azure Portal, seleccione **Migrate your environment to Azure** (Migrar su entorno a Azure) y, después, siga las instrucciones paso a paso.

::: zone-end

## <a name="migration-tools"></a>[Herramientas de migración](#tab/MigrationTools)

Esta guía es la ruta de acceso sugerida para su primera migración a Azure, ya que le mostrará la metodología y las herramientas nativas de la nube que se usan con más frecuencia durante la migración a Azure. Estas herramientas se presentan en las páginas siguientes:

> [!div class="checklist"]
>
> - **Evaluación de la adecuación técnica de cada carga de trabajo.** Valide la preparación técnica y la idoneidad para la migración.
> - **Migración de los servicios.** Realice la migración real mediante la replicación de recursos locales en Azure.
> - **Administrar costos y facturación**: Conozca las herramientas necesarias para controlar los costos en Azure.
> - **Optimización y promoción.** Optimice el equilibrio entre el costo y el rendimiento antes de promocionar la carga de trabajo a producción.
> - **Obtención de ayuda.** Obtenga ayuda y soporte técnico durante las actividades de migración o posteriores a ella.

Se supone que ya se ha implementado una zona de aterrizaje según los procedimientos recomendados en la [metodología de preparación de Cloud Adoption Framework](../../ready/index.md).

## <a name="when-to-use-this-guide"></a>[Cuándo utilizar esta guía](#tab/WhenToUseThisGuide)

Si bien las herramientas analizadas en esta guía son compatibles con una amplia variedad de escenarios de migración, esta guía se centrará en esfuerzos de ámbito limitado con _complejidad mínima_. Para determinar si esta guía de migración es adecuada para el proyecto, considere si las siguientes condiciones se pueden aplicar a su situación:

- Las cargas de trabajo para la migración inicial no son críticas y no contienen información confidencial.
- Va a migrar un entorno homogéneo.
- Solo unas pocas unidades de negocio necesitan alinearse para completar la migración.
- No tiene previsto automatizar la migración completa.
- Está migrando un pequeño número de servidores.
- La asignación de dependencias de los componentes que se van a migrar es fácil de definir.
- Su sector tiene requisitos normativos mínimos relevantes para esta migración.

Si alguna de estas condiciones no es aplicable a su situación, considere la posibilidad de usar en su lugar otros [procedimientos recomendados para la migración a la nube](../azure-best-practices/index.md). También le recomendamos que solicite la asistencia de uno de nuestros equipos o asociados de Microsoft para realizar migraciones más complejas. Los clientes que se relacionan con Microsoft o con asociados certificados tienen más éxito en estos escenarios. Para más información sobre cómo solicitar asistencia, consulte esta guía.

<!-- markdownlint-enable MD033 -->

::: zone target="docs"

Para más información, consulte:

- [Procedimientos recomendados para la migración a la nube](../azure-best-practices/index.md)

::: zone-end
