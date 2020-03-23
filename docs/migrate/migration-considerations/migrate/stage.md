---
title: Actividades de almacenamiento provisional durante una migración
description: Use Cloud Adoption Framework para Azure para comprender las actividades de almacenamiento provisional y las entregas asociadas necesarias durante una migración.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 491080353d6cf67009720359257d9f1b8bbfdd6d
ms.sourcegitcommit: 5411c3b64af966b5c56669a182d6425e226fd4f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79311763"
---
# <a name="understand-staging-activities-during-a-migration"></a>Descripción de las actividades de almacenamiento provisional durante una migración

Tal como se describe en el artículo sobre los modelos de promoción, el *almacenamiento provisional* es el punto en el que se han migrado los recursos a la nube. Sin embargo, todavía no están preparados para promoverse a producción. Este suele ser el último paso del proceso de migración de una migración. Después del almacenamiento provisional, la carga de trabajo la administra un equipo de operaciones de TI o de operaciones en la nube para prepararla para su uso en producción.

## <a name="deliverables"></a>Resultados

Es posible que los recursos almacenados provisionalmente no estén listos para su uso en producción. Hay varias comprobaciones de disponibilidad para la producción que se deben finalizar antes de que esta fase se considere completa. A continuación, se muestra una lista de los resultados que se suelen asociar con la finalización de la etapa del almacenamiento provisional de los recursos.

- **Pruebas automatizadas.** Las pruebas automatizadas disponibles para validar el rendimiento de la carga de trabajo deben ejecutarse antes de concluir el proceso de almacenamiento provisional. Una vez que el recurso sale del almacenamiento provisional, se finaliza la sincronización con el sistema de origen original. Por lo tanto, es más difícil volver a implementar los recursos replicados una vez que los recursos se almacenan provisionalmente para su optimización.
- **Documentación de la migración.** La mayoría de las herramientas de migración pueden generar un informe automatizado de los recursos que se están migrando. Antes de concluir la actividad de almacenamiento provisional, todos los recursos migrados deben documentarse para mayor claridad.
- **Documentación de la configuración.** Cualquier cambio realizado en un recurso (durante la corrección, la replicación o el almacenamiento provisional) debe documentarse para la disponibilidad operativa.
- **Documentación del trabajo pendiente.** El trabajo pendiente de migración se debe actualizar para reflejar la carga de trabajo y los recursos almacenados provisionalmente.

## <a name="next-steps"></a>Pasos siguientes

Después de probar y documentar los recursos almacenados provisionalmente, puede continuar con las [actividades de optimización](../optimize/index.md).

> [!div class="nextstepaction"]
> [Optimización de las cargas de trabajo migradas](../optimize/index.md)
