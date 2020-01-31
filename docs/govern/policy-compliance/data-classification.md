---
title: ¿Qué es la clasificación de datos?
description: La clasificación de datos permite determinar y asignar valor a los datos de la organización y es un punto de partida común para la gobernanza.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 1f476aaccfc88eab4a2bea1db17e7b1d33f31ee9
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76805088"
---
<!-- markdownlint-disable MD026 -->

# <a name="what-is-data-classification"></a>¿Qué es la clasificación de datos?

La clasificación de datos permite determinar y asignar valor a los datos de la organización y es un punto de partida común para la gobernanza. El proceso de clasificación de datos clasifica los datos por confidencialidad e impacto empresarial a fin de identificar los riesgos. Cuando los datos están clasificados, se pueden administrar de formas que protegen aquellos confidenciales o importantes frente al robo o la pérdida.

## <a name="understand-data-risks-then-manage-them"></a>Comprender los riesgos de los datos y administrarlos

Para administrar cualquier riesgo, hay que entenderlo. En el caso de la responsabilidad por infracción de datos, ese conocimiento comienza con la clasificación de datos. La clasificación de datos es el proceso de asociar una característica de metadatos a cada recurso de un entorno digital, que identifica el tipo de datos asociado con ese recurso.

Cualquier recurso que se haya identificado como un posible candidato para la migración o la implementación en la nube debería tener metadatos documentados para registrar la clasificación de los datos, la importancia para la empresa y la responsabilidad de facturación. Estos tres puntos de clasificación pueden recorrer un largo camino para comprender y mitigar los riesgos.

## <a name="classifications-microsoft-uses"></a>Clasificaciones que usa Microsoft

La siguiente es una lista de clasificaciones que usa Microsoft. Según su sector o los requisitos de seguridad existentes, puede que ya existan estándares de clasificación de datos dentro de su organización. Si no existe ningún estándar, es posible que quiera usar esta clasificación de ejemplo para comprender mejor el patrimonio digital propio y el perfil de riesgo.

- **No empresarial:** datos de la vida personal que no pertenecen a Microsoft.
- **Pública:** datos comerciales públicamente disponibles y aprobados para uso público.
- **General:** datos empresariales que no están destinados a una audiencia pública.
- **Confidencial:** datos empresariales que pueden causar daños a Microsoft si se compartieran en exceso.
- **Extremadamente confidencial:** datos empresariales que podrían causar graves daños a Microsoft si se compartieran en exceso.

## <a name="tagging-data-classification-in-azure"></a>Etiquetado de la clasificación de datos en Azure

Las etiquetas de recursos son una buena opción para el almacenamiento de metadatos; puede usar estas etiquetas para aplicar información de clasificación de datos a recursos implementados. Aunque el etiquetado de los recursos en la nube por clasificación no sustituye a un proceso de clasificación de datos formal, proporciona una valiosa herramienta para administrar recursos y aplicar directivas. [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) es una solución excelente para ayudarle a clasificar _datos_ independientemente de dónde estén ubicados (en el entorno local, en Azure, en alguna otra ubicación) y se debería tener en cuenta como parte de una estrategia de clasificación general. Tenga en cuenta esta herramienta como parte de una estrategia general de clasificación.

Para obtener más información acerca del etiquetado de recursos, consulte [Uso de etiquetas para organizar los recursos de Azure](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-using-tags).

## <a name="next-steps"></a>Pasos siguientes

Aplique clasificaciones de datos durante una de las guías prácticas de gobernanza.

> [!div class="nextstepaction"]
> [Seleccione una guía práctica de gobernanza](../guides/index.md)
