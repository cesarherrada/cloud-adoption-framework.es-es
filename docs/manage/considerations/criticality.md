---
title: 'Importancia crítica para la empresa: administración y operaciones de la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Importancia crítica para la empresa: administración y operaciones de la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 290fcf7093f128c1415bbf960d65074d12490ae1
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683644"
---
# <a name="business-criticality-in-cloud-management"></a>Importancia crítica para la empresa en la administración de la nube

En cada empresa, existe un pequeño número de cargas de trabajo que son demasiado importantes como para que produzcan errores. Cuando esas cargas de trabajo experimentan interrupciones o una degradación del rendimiento, se puede sentir un efecto adverso sobre los ingresos y la rentabilidad en toda la empresa. Estas cargas de trabajo se consideran críticas.

En el otro extremo del espectro, pueden pasar meses sin que se utilicen algunas cargas de trabajo. En este caso, tampoco se quiere que experimenten un bajo rendimiento o interrupciones, aunque el efecto será aislado y limitado.

Comprender la importancia crítica de cada carga de trabajo de la cartera de TI es el primer paso hacia los compromisos mutuos con la administración de la nube.
En la imagen siguiente se describe una alineación común entre la escala de importancia crítica que se debe seguir y los compromisos estándar realizados por la empresa.

![Alineación del nivel de administración e importancia crítica](../../_images/manage/cloud-criticality-alignment.png)

## <a name="criticality-scale"></a>Escala de importancia crítica

El primer paso en cualquier trabajo de alineación de la importancia crítica para la empresa es la creación de una escala. A continuación, se muestra una escala de ejemplo que se puede usar como referencia o plantilla para crear la suya propia.

|Grado de importancia  |Visión empresarial  |
|---------|---------|
|Crítica|Afecta a la misión de la empresa y puede influir considerablemente en el balance de pérdidas y ganancias corporativas.|
|Crítica para la unidad|Afecta a la misión de una unidad de negocio específica y al balance de pérdidas y ganancias de las unidades de negocio.|
|Alto|Aunque puede que no entorpezca la misión, afecta a los procesos de importancia alta. En el caso de las interrupciones, las pérdidas mensurables se pueden cuantificar.|
|Mediano|Lo más probable es que afecte a los procesos. Las pérdidas son bajas o imperceptibles, pero pueden producirse daños en la marca o pérdidas en la etapa inicial de la producción.|
|Bajo|El efecto sobre los procesos empresariales es inconmensurable. No es probable que se produzcan daños en la marca o pérdidas en la etapa inicial de producción. Lo más probable es que haya un efecto localizado en un solo equipo.|
|No compatible|Ningún propietario, equipo o proceso de negocio asociado a esta carga de trabajo puede justificar una inversión en la administración continua de la carga de trabajo.|

Es habitual que las empresas incluyan clasificaciones adicionales de importancia crítica específicas de un sector, segmento vertical o proceso empresarial determinado. Entre los ejemplos de clasificaciones adicionales se incluyen:

- **Crítica para el cumplimiento:** en sectores muy regulados, algunas cargas de trabajo pueden ser críticas como parte de las labores de cumplimiento de la normativa.
- **Crítica para la seguridad:** es posible que algunas cargas de trabajo no sean críticas, pero las interrupciones podrían provocar la pérdida de datos o el acceso no deseado a información protegida.
- **Crítica para la protección:** cuando la vida o la seguridad física de empleados y clientes están en juego durante una interrupción, puede ser aconsejable clasificar las cargas de trabajo como críticas para la protección.

## <a name="importance-of-accurate-criticality"></a>Valor de la importancia crítica precisa

Más adelante en este proceso, el equipo de administración de la nube usará esta clasificación para determinar la cantidad de trabajo necesaria para cumplir los niveles de importancia crítica alineados. En entornos locales, la administración de operaciones se procura de forma central y se trata como una carga empresarial necesaria, con poco o ningún costo operativo adicional. En la nube, la administración de operaciones (como la de toda la nube) se procura por recurso según los costos operativos mensuales.

Dado que hay un costo claro y directo para la administración de operaciones en la nube, es importante alinear correctamente los costos y las escalas de importancia crítica deseadas.

## <a name="select-a-default-criticality"></a>Selección de una importancia crítica predeterminada

La revisión inicial de cada carga de trabajo de la cartera podría llevar mucho tiempo. Para tener la seguridad de que este trabajo no bloquea la estrategia en la nube más amplia, se sugiere llegar a un acuerdo con la empresa sobre la importancia crítica predeterminada que se aplicará a todas las cargas de trabajo.

En función de la escala de importancia crítica anterior, se recomienda usar el nivel "medio" como predeterminado. De esta forma, el equipo de estrategia en la nube podrá identificar rápidamente las cargas de trabajo que requieren un nivel más alto de importancia crítica.

## <a name="using-the-template"></a>Uso de la plantilla

Los siguientes pasos se aplican a los lectores que utilizan el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube.

1. La escala de importancia crítica se puede registrar en la pestaña de escala del libro.
2. Cada carga de trabajo del "ejemplo" o de la "plantilla limpia" debe actualizarse para reflejar el nivel de importancia predeterminado en la columna "importancia crítica".
3. La empresa debe introducir los valores correctos para reflejar las posibles desviaciones del nivel de importancia crítica predeterminado.

## <a name="next-steps"></a>Pasos siguientes

Una vez definida la importancia crítica, [calcule y registre el efecto para la empresa](./impact.md).

> [!div class="nextstepaction"]
> [Cálculo y registro del efecto para la empresa](./impact.md)
