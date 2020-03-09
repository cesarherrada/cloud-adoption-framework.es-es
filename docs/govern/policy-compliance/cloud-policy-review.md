---
title: Revisión de una directiva de nube
description: Aprenda a modernizar las directivas de TI corporativas existentes para proporcionar un nivel equivalente de administración de riesgos para los recursos basados en la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: e4235830eee8e57581214f3eabb46c32ebcf975b
ms.sourcegitcommit: af45c1c027d7246d1a6e4ec248406fb9a8752fb5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77709131"
---
<!-- markdownlint-disable MD026 -->

# <a name="conduct-a-cloud-policy-review"></a>Revisión de una directiva de nube

La revisión de una directiva de nube es el primer paso hacia la [madurez de la gobernanza](../index.md) de la nube. El objetivo de este proceso es modernizar las directivas de TI corporativas existentes. Una vez finalizada esta tarea, las directivas actualizadas proporcionan un nivel equivalente de mitigación de los riesgos para los recursos en la nube. En este artículo se explica el proceso de revisión de una directiva en la nube y su importancia.

## <a name="why-perform-a-cloud-policy-review"></a>¿Por qué realizar la revisión de una directiva en la nube?

La mayoría de las empresas administran la TI mediante la ejecución de procesos que están en consonancia con las directivas en vigor. En las pequeñas empresas, estas directivas pueden ser anecdóticas y los procesos se definen de manera imprecisa. A medida que las empresas evolucionan para convertirse en grandes empresas, las directivas y los procesos tienden a documentarse con mayor claridad y a ejecutarse de manera coherente.

A medida que las empresas maduran las directivas de TI corporativas, las dependencias de las decisiones técnicas anteriores tienden a filtrarse en las directivas en vigor. Por ejemplo, es habitual observar procesos de recuperación ante desastres que incluyen directivas que exigen copias de seguridad en cinta fuera del sitio. En esta inclusión, se supone que existe una dependencia de un tipo de tecnología (copias de seguridad en cinta) que puede que ya no sea la solución más importante.

Las transformaciones a la nube crean un punto de inflexión natural para reconsiderar las decisiones que se tomaron en el pasado en las directivas heredadas. Las funcionalidades técnicas y los procesos predeterminados cambian considerablemente en la nube, al igual que los riesgos heredados. Tomando como referencia el ejemplo anterior, la directiva de copia de seguridad en cinta derivó del riesgo de tener un único punto de error al mantener los datos en una sola ubicación y la necesidad empresarial de minimizar el perfil de riesgo mediante la mitigación de este riesgo. En una implementación en la nube, hay varias opciones que proporcionan la misma mitigación de riesgos, con objetivos de tiempo de recuperación (RTO) mucho menores. Por ejemplo:

- Una solución nativa en la nube podría habilitar la replicación geográfica de la base de datos de Azure SQL Database.
- Una solución híbrida podría usar Azure Site Recovery para replicar una carga de trabajo IaaS en Azure.

Al ejecutar una transformación en la nube, las directivas suelen regular muchas de las herramientas, servicios y procesos disponibles para los equipos de adopción de la nube. Si esas directivas se basan en tecnologías heredadas, pueden obstaculizar los esfuerzos del equipo para realizar cambios. En el peor de los casos, el equipo de migración ignora completamente directivas importantes para aplicar soluciones alternativas. Ninguno es un resultado aceptable.

## <a name="the-cloud-policy-review-process"></a>Proceso de revisión de directivas en la nube

Las revisiones de directivas de nube alinean las directivas de seguridad de TI y de gobernanza de TI existentes con las [cinco materias de gobernanza de la nube](../index.md): [administración de costos](../cost-management/index.md), [base de referencia de seguridad](../security-baseline/index.md), [base de referencia de identidad](../identity-baseline/index.md), [coherencia de recursos](../resource-consistency/index.md) y [aceleración de la implementación](../deployment-acceleration/index.md).

En cada una de estas materias, siga estos pasos en el proceso de revisión:

1. Revise las directivas locales existentes relacionadas con la materia específica, para lo que debe buscar dos puntos de datos clave: dependencias heredadas y riesgos empresariales identificados.
2. Evalúe cada riesgo empresarial formulando una pregunta sencilla: "¿El riesgo empresarial todavía existe en un modelo de nube?"
3. Si el riesgo aún existe, vuelva a escribir la directiva y documente la mitigación empresarial necesaria, no la solución técnica.
4. Revise la directiva actualizada con los equipos de adopción de la nube para entender las posibles soluciones técnicas para la mitigación necesaria.

## <a name="example-of-a-policy-review-for-a-legacy-policy"></a>Ejemplo de revisión de una directiva heredada

Para proporcionar un ejemplo del proceso, vamos a volver a usar la directiva de copia de seguridad en cinta de la sección anterior:

- Una directiva corporativa exige copias de seguridad en cinta fuera del sitio para todos los sistemas de producción. En esta directiva, puede ver dos puntos de datos de interés:
  - Dependencia heredada en una solución de copia de seguridad en cinta.
  - Un riesgo empresarial asumido asociado con el almacenamiento de copias de seguridad en la misma ubicación física que el equipo de producción.
- ¿Existe todavía el riesgo? Sí. Incluso en la nube, la dependencia de una única instalación plantea algunos riesgos. Existe una probabilidad más baja de que este riesgo afecte a la empresa en comparación con el riesgo planteado en la solución local, pero el riesgo aún existe.
- Vuelva a escribir la directiva. En caso de que se produzca un desastre que afecte a todo el centro de datos, deben existir métodos para restaurar los sistemas de producción en un plazo de 24 horas después de la interrupción en otro centro de datos y en una ubicación geográfica distinta.
  - También es importante tener en cuenta que la escala de tiempo especificada en el requisito anterior puede haberse establecido por restricciones técnicas que ya no están presentes en la nube. Asegúrese de que comprende las restricciones técnicas y las funcionalidades de la nube antes de aplicar simplemente un RTO/RPO heredado.
- Revise el caso con los equipos de adopción de la nube. Según la solución implementada, existen varias formas de cumplir esta directiva de coherencia de recursos.

## <a name="next-steps"></a>Pasos siguientes

Obtenga más información sobre cómo incluir la clasificación de datos en su estrategia de gobernanza de la nube.

> [!div class="nextstepaction"]
> [Clasificación de los datos](./data-classification.md)
