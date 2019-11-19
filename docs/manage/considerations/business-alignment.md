---
title: 'Alineación empresarial: administración y operaciones en la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Alineación empresarial: administración y operaciones en la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: deeb663a344bb3eb4e8ecc9af307da5ec1348b7a
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73565213"
---
# <a name="create-business-alignment-in-cloud-management"></a>Crear la alineación empresarial en la administración en la nube

En entornos locales, TI administra los activos de TI (aplicaciones, máquinas virtuales, hosts de máquina virtual, discos, servidores, dispositivos y orígenes de datos) para admitir operaciones de carga de trabajo. En términos de TI, una carga de trabajo es una colección de activos de TI que admiten una operación empresarial específica. Para ayudar a respaldar las operaciones empresariales, la administración de TI ofrece procesos diseñados para minimizar las interrupciones de esos recursos. Cuando una organización pasa a la nube, la administración y las operaciones cambian un poco, lo que crea una oportunidad para desarrollar una mejor alineación empresarial.

## <a name="business-vernacular"></a>Jerga empresarial

El primer paso para crear la alineación empresarial es garantizar la alineación de los términos. La administración de TI, como la mayoría de las profesiones de ingeniería, ha acumulado una colección de jerga o de términos muy técnicos. Estos términos pueden generar confusión en las partes interesadas del negocio y dificultar la asignación de servicios de administración al valor empresarial.

Afortunadamente, el proceso para desarrollar una estrategia de adopción de la nube y un plan de adopción de la nube crean una oportunidad ideal para la reasignación de estos términos. El proceso también crea oportunidades para replantear los compromisos para la administración operativa, en colaboración con la empresa. En la siguiente serie de artículos se describe este nuevo enfoque en tres términos específicos que pueden ayudar a mejorar las conversaciones entre las partes interesadas del negocio: 

- **[Importancia crítica](./criticality.md):** asignación de cargas de trabajo a procesos empresariales. Clasificación del grado de importancia para enfocar las inversiones.
- **[Impacto](./impact.md):** comprensión del impacto de las posibles interrupciones para ayudar a evaluar la rentabilidad de la inversión para la administración en la nube.
- **[Compromiso](./commitment.md):** desarrollo de verdaderas asociaciones, mediante la creación y la documentación de contratos *con la empresa*.

> [!NOTE]
> Subyacentes a estos términos hay términos de TI clásicos como SLA, RTO y RPO. La asignación de términos empresariales y de TI específicos se trata con más detalle en el artículo sobre el [compromiso](./commitment.md).

## <a name="ops-management-planning-workbook"></a>Libro de planificación de la administración de operaciones

Para ayudar a capturar decisiones que se derivan de esta conversación sobre la alineación de los términos, existe un [libro de administración de operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) disponible en el sitio de GitHub. Este libro no supone un contrato de nivel de servicio ni cálculos de costos. Solo sirve de ayuda para capturar estas medidas y prever los esfuerzos para evitar el retorno de pérdidas.

Como alternativa, estas mismas cargas de trabajo y recursos asociados podrían etiquetarse directamente en Azure, si las soluciones ya están implementadas en la nube.

## <a name="next-steps"></a>Pasos siguientes

Comience a crear la alineación empresarial definiendo el [grado de importancia de la carga de trabajo](./criticality.md).

> [!div class="nextstepaction"]
> [Definir el grado de importancia de la carga de trabajo](./criticality.md)
