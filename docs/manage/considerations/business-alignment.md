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
ms.openlocfilehash: 9c6884d57b9238f58921b14ec3ddbbe3623506af
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72558590"
---
# <a name="create-business-alignment-in-cloud-management"></a>Crear la alineación empresarial en la administración en la nube

En entornos locales, TI administra los activos de TI (aplicaciones, máquinas virtuales, hosts de máquina virtual, discos, servidores, dispositivos y orígenes de datos) para admitir operaciones de carga de trabajo. En términos de TI, una carga de trabajo es una colección de activos de TI que admiten una operación empresarial específica. En entornos locales, la administración de TI ofrece un diseño de procesos para minimizar las interrupciones en los activos de TI, en un intento de minimizar las interrupciones en las operaciones empresariales de soporte técnico. Al pasar a la nube, la administración y las operaciones se desplazan un poco, lo que crea una oportunidad para desarrollar una mejor alineación empresarial.

## <a name="business-vernacular"></a>Jerga empresarial

El primer paso para crear la alineación empresarial es la alineación de los términos. La administración de TI, como la mayoría de las profesiones de ingeniería, incluye bastante jerga o términos muy técnicos. Estos términos pueden dar lugar a confusión en las partes interesadas del negocio y dificultar la asignación de servicios de administración a valor empresarial.

Afortunadamente, los procesos para desarrollar una estrategia de adopción de la nube y un plan de adopción de la nube crean una idea de la situación para la reasignación de los términos. También crea una gran oportunidad para replantear los compromisos para la administración operativa, en colaboración con la empresa. En la siguiente serie de artículos se describe este nuevo enfoque en tres términos específicos que pueden mejorar las conversaciones con las partes interesadas del negocio:

- **[Grado de importancia](./criticality.md)** : asignación de cargas de trabajo a procesos empresariales. Clasificación del grado de importancia para enfocar las inversiones.
- **[Impacto](./impact.md)** : comprensión del impacto de las posibles interrupciones para ayudar a evaluar la rentabilidad de la inversión para la administración en la nube.
- **[Compromiso](./commitment.md)** : desarrollo de verdaderas asociaciones, mediante la creación y la documentación de contratos **con la empresa**.

> [!NOTE]
> Debajo de cada uno de estos términos hay términos de TI clásicos como SLA, RTO y RPO. La asignación de términos empresariales y de TI se trata con más detalle en el artículo sobre el compromiso.

## <a name="ops-management-planning-workbook"></a>Libro de planificación de la administración de operaciones

Para ayudarle a capturar decisiones como resultado de esta conversación, está disponible un [libro de administración de operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) en nuestro repositorio GitHub. Este libro no supone un contrato de nivel de servicio ni cálculos de costos. Solo sirve como guía para capturar las medidas y prever los esfuerzos para evitar el retorno de pérdidas.

Como alternativa, estas mismas cargas de trabajo y recursos asociados podrían etiquetarse directamente en Azure, si las soluciones ya están implementadas en la nube.

## <a name="next-steps"></a>Pasos siguientes

Comience a crear la alineación empresarial definiendo el [grado de importancia de la carga de trabajo](./criticality.md).

> [!div class="nextstepaction"]
> [Definir el grado de importancia de la carga de trabajo](./criticality.md)
