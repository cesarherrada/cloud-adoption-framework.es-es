---
title: Procedimientos recomendados de migración de Azure
description: Introducción a los procedimientos recomendados de migración de Azure
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 5cc4a0cfdfe605fdd374055e782db2f0ce47c13f
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76807298"
---
# <a name="azure-migration-best-practices"></a>Procedimientos recomendados de migración de Azure

Azure proporciona varias herramientas que facilitan el proceso de migración. Esta sección de Cloud Adoption Framework está diseñada para ayudar a los lectores a implementar dichas herramientas de acuerdo con los procedimientos recomendados para la migración. Estos procedimientos recomendados se alinean con uno de los procesos del modelo de migración de Cloud Adoption Framework que se representa a continuación.

Expanda cualquier proceso de la tabla de contenido de la izquierda para ver los procedimientos recomendados que son normalmente necesarios durante dicho proceso.

![Modelo de migración de Cloud Adoption Framework](../../_images/operational-transformation-migrate.png)

> [!NOTE]
> La valoración de los recursos y la planeación del patrimonio digital representan dos niveles diferentes de valoración y planeación de la migración:
>
> - **Planeación del patrimonio digital:** El patrimonio digital se planea o racionaliza durante la planeación, con el fin de establecer un trabajo pendiente de migración global. Sin embargo, dicho plan se basa en algunas suposiciones y detalles que es preciso validar para poder migrar a una carga de trabajo.
> - **Valoración de recursos:** Los recursos individuales de una carga de trabajo se valoran antes de que esta se migre, con el fin de evaluar la compatibilidad de la nube y conocer las restricciones de arquitectura y tamaño. Este proceso valida las suposiciones iniciales y proporciona los detalles necesarios para migrar un recurso individual.
