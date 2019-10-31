---
title: 'Innovación en la nube: Democratización de los datos'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Introducción a la innovación en la nube: democratización de los datos'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: c0ef1165fc416814e0563ec29c4ad5901a83b032
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683276"
---
# <a name="democratize-data"></a>Democratización de los datos

El carbón, el aceite y el potencial humano eran los tres recursos más valiosos durante la revolución industrial. Estos recursos creaban compañías, movían los mercados y, en última instancia, cambiaban países. En la economía digital, hay tres recursos igualmente importantes: datos, dispositivos y potencial humano. En cada uno de estos recursos hay un fantástico potencial de innovación. En cualquier trabajo de innovación, los datos son el nuevo aceite.

En todas las empresas de hoy en día, hay depósitos de datos que podrían aprovecharse para buscar y satisfacer las necesidades de los clientes con mayor rapidez. Lamentablemente, el proceso de minería de datos para impulsar la innovación es muy costoso y lento. Muchas de las soluciones más valiosas para las necesidades de los clientes se desestiman porque las personas adecuadas no pueden acceder a los datos que necesitan.

La democratización de los datos es el proceso de poner estos datos en las manos adecuadas para impulsar la innovación. Este proceso puede tener varias formas, pero generalmente incluye soluciones para datos sin procesar ingeridos o integrados, la centralización de los datos, el uso compartido de los datos y la protección de los datos. Cuando se realiza correctamente, los expertos de la empresa pueden aprovechar los datos para probar los supuestos. En muchos casos, los equipos de adopción de la nube pueden [crear con empatía con el cliente](./build.md) usando solo los datos, lo que tiene un impacto rápido en las necesidades existentes de los clientes.

## <a name="process-of-democratizing-data"></a>Proceso de democratización de los datos

En las siguientes fases se guiarán las decisiones y los enfoques necesarios para adoptar una solución que democratiza los datos. Pueden que no sean necesarias todas las fases para crear una solución específica. Sin embargo, deben evaluarse todas al crear una solución para la hipótesis de un cliente. Cada una de ellas proporciona un enfoque único para la creación de soluciones innovadoras.

![Proceso de democratización de los datos](../../_images/innovate/democratize-data.png)

### <a name="share-data"></a>Compartir datos

Al [crear con empatía con el cliente](./build.md), todos los procesos se centran en la necesidad del cliente frente a una solución técnica. La democratización de los datos no es una excepción, por lo que comenzaremos con el uso compartido de los datos. Para democratizar los datos, debe incluir una solución que comparta los datos con un consumidor de datos. El consumidor de los datos puede ser un cliente directo o un servidor proxy que toma decisiones para los clientes. Los consumidores de datos aprobados tienen la capacidad de realizar análisis, preguntas e informes con los datos centralizados, sin soporte técnico del personal de TI.

Muchas innovaciones de éxito se han iniciado como soluciones viables mínimas que proporcionan procesos manuales y controlados por datos en nombre del cliente. En este modelo, un empleado es el consumidor de los datos. Ese empleado utiliza datos para ayudar al cliente. Cada vez que el cliente se pone en contacto con el soporte manual, se puede probar y validar una hipótesis. Este enfoque suele ser un medio rentable de probar una hipótesis centrada en el cliente antes de realizar grandes inversiones en soluciones integradas.

Las principales herramientas para compartir datos directamente con los consumidores de datos son los informes de autoservicio o datos insertados en otras experiencias mediante herramientas como [Power BI](https://docs.microsoft.com/power-bi).

> [!NOTE]
> Antes de compartir datos, es importante tener en cuenta las siguientes secciones. El uso compartido de datos puede requerir gobernanza para proteger los datos compartidos. Además, los datos pueden estar diseminados en varias nubes y podrían requerir centralización. Gran parte de los datos pueden residir incluso dentro de las aplicaciones, lo que requerirá recopilar los datos antes de compartirlos.

### <a name="govern-data"></a>Gobernanza de los datos

El uso compartido de datos puede generar rápidamente un producto viable mínimo que se puede usar en las conversaciones con los clientes. Sin embargo, los datos solo son datos únicamente. Para convertir los datos compartidos en conocimientos procesables, hace falta algo más. Una vez que se ha validado una hipótesis mediante el uso compartido de datos, la siguiente fase de desarrollo suele ser la regulación de los datos.

La gobernanza de los datos es un tema amplio que podría requerir su propio marco dedicado. Esto queda fuera del ámbito de [Cloud Adoption Framework](../../index.md). Sin embargo, hay algunos aspectos de la gobernanza de los datos que se deben tener en cuenta en cuanto se valide la hipótesis del cliente. Estos son algunos ejemplos de estas preguntas:

- **¿Los datos compartidos son confidenciales?** [Los datos se deben clasificar](../../govern/policy-compliance/data-classification.md) antes de hacer cualquier uso compartido público para proteger los intereses de los clientes y de la empresa.
- **Si los datos son confidenciales, ¿se han protegido?** La protección de los datos confidenciales debe ser un requisito en todo dato democratizado. La carga de trabajo de ejemplo centrada en [proteger las soluciones de datos](https://docs.microsoft.com/azure/architecture/data-guide/scenarios/securing-data-solutions.md) proporciona algunas referencias para proteger los datos.
- **¿Los datos están catalogados?** Capturar detalles sobre los datos que se comparten ayuda a administrar los datos a largo plazo. Las herramientas para documentar datos, como Azure Data Catalog, pueden hacer que este proceso sea mucho más fácil en la nube. Las instrucciones sobre [anotación de los datos](https://docs.microsoft.com/azure/data-catalog/data-catalog-how-to-annotate) y [documentación de los orígenes de datos](https://docs.microsoft.com/azure/data-catalog/data-catalog-how-to-documentation) pueden ayudar a acelerar el proceso.

Cuando la democratización de los datos es importante para una hipótesis centrada en el cliente, la gobernanza de los datos compartidos debe estar en alguna parte del plan de lanzamiento para proteger a los clientes, los consumidores de los datos y la empresa.

### <a name="centralize-data"></a>Centralización de los datos

Cuando se interrumpe el flujo de datos en un entorno de TI, las oportunidades de innovación pueden ser muy limitadas, costosas y lentas. La nube proporciona nuevas oportunidades para centralizar los datos en varios silos de datos. Cuando es necesario centralizar varios orígenes de datos para [crear con empatía con el cliente](./build.md), la nube puede acelerar la prueba de los supuestos.

> [!CAUTION]
> La centralización de los datos es un punto de riesgo común en cualquier proceso de innovación. Cuando la centralización de datos supone una [demanda técnica](./build.md#reduce-complexity-and-delay-technical-spikes) y no una fuente de valor del cliente, se recomienda retrasar la centralización hasta que se haya validado la hipótesis del cliente.

Si es necesario centralizar los datos, el primer paso es definir el almacén de datos adecuado para los datos centralizados. El enfoque recomendado es establecer un almacenamiento de datos en la nube. Esta opción escalable proporcionará una ubicación central para todos los datos. Este tipo de solución está disponible en las opciones de procesamiento analítico en línea (OLAP) o de macrodatos.

Las arquitecturas de referencia para las soluciones [OLAP](https://docs.microsoft.com/azure/architecture/data-guide/relational-data/online-analytical-processing) y de [macrodatos](https://docs.microsoft.com/azure/architecture/data-guide/big-data) pueden ayudarle a elegir la solución más pertinente en Azure. Si se requiere una solución híbrida, la arquitectura de referencia para la [extensión de los datos locales](https://docs.microsoft.com/azure/architecture/data-guide/scenarios/hybrid-on-premises-and-cloud) también puede ayudar a acelerar el desarrollo de soluciones.

> [!IMPORTANT]
> En función de las necesidades del cliente y la solución correspondiente, quizás una solución más sencilla sea suficiente. El arquitecto de la nube debe desafiar al equipo para que considere soluciones de menor costo que podrían permitir una validación más rápida de la hipótesis del cliente, especialmente durante las primeras fases del desarrollo. En la sección siguiente sobre la recopilación de datos se describen algunos escenarios en los que es posible que se necesite una solución diferente.

### <a name="collect-data"></a>Recopilación de datos

Cuando los datos deben centralizarse para satisfacer las necesidades de los clientes, es muy probable que también sea necesario recopilar los datos de varios orígenes y pasarlos al almacén de datos centralizado. Hay dos formas principales de recopilación de datos: integración e ingesta. Cada una de ellas proporciona un medio diferente para la recopilación de datos.

**Integración:** los datos existentes que ya residen en un almacén de datos se pueden integrar en el almacén de datos centralizado mediante técnicas tradicionales de movimiento de datos. Esto es especialmente frecuente en escenarios que implican el almacenamiento de datos en varias nubes. Estas técnicas consisten en extraer los datos del almacén de datos existente. A continuación, los datos se cargan en el almacén de datos central. En algún momento de este proceso, los datos suelen transformarse para facilitar su uso y que sean más pertinentes en el almacén central.

Las herramientas basadas en la nube han convertido estas técnicas en herramientas de pago por uso, lo que reduce las barreras iniciales para la centralización y recopilación de los datos. Herramientas como Data Migration Service y Data Factory son dos ejemplos comunes de Azure. La arquitectura de referencia para una [factoría de datos con un almacén de datos OLAP](https://docs.microsoft.com/azure/architecture/data-guide/relational-data/etl) proporciona un ejemplo de este tipo de solución.

**Ingesta:** algunos datos no están en ningún almacén de datos existente. Cuando estos datos transitorios son una fuente principal de innovación, se deben tener en cuenta enfoques alternativos. Los datos transitorios se pueden encontrar en diversos orígenes, tales como aplicaciones, API, flujos de datos, dispositivos IoT, cadenas de bloques, caché de aplicaciones, contenido multimedia o incluso archivos sin formato.

Estas diversas formas de datos se pueden integrar en un almacén de datos central en una solución OLAP o de macrodatos. Sin embargo, para las primeras iteraciones de los ciclos de creación-medida-aprendizaje, una solución de procesamiento transaccional en línea (OLTP) puede ser más que suficiente para validar una hipótesis del cliente. Las soluciones OLTP no ofrecen la mejor calidad en escenarios de informes. Sin embargo, cuando se [crea con empatía con el cliente](./build.md), las necesidades del cliente tienen prioridad sobre las decisiones técnicas sobre herramientas. Una vez validada la hipótesis del cliente a escala, puede ser necesaria una plataforma más adecuada. La arquitectura de referencia de los [almacenes de datos OLTP](https://docs.microsoft.com/azure/architecture/data-guide/relational-data/online-transaction-processing) puede ayudar a determinar qué almacén de datos es el más adecuado para la solución.

**Virtualización:** La integración y la ingesta de datos a veces pueden ralentizar la innovación. Si ya hay disponible una solución para virtualizar los datos, podría ser un enfoque más pertinente. La ingesta y la integración pueden duplicar los requisitos de almacenamiento y desarrollo, agregar latencia de datos, aumentar la superficie expuesta a ataques, introducir problemas de calidad y aumentar el trabajo de gobernanza. La virtualización de los datos es una alternativa más moderna que deja los datos originales en una ubicación única y crea consultas de paso a través o almacenadas en caché de los datos de origen.

SQL Server 2017 y Azure SQL Data Warehouse admiten [PolyBase](/sql/relational-databases/polybase/polybase-guide), que es el enfoque de virtualización de datos que se usa con más frecuencia en Azure.

## <a name="next-steps"></a>Pasos siguientes

Cuando ya hay una estrategia para la democratización de los datos, el siguiente paso es evaluar los enfoques a la [interacción con los clientes mediante aplicaciones](./apps.md).

> [!div class="nextstepaction"]
> [Interacción con los clientes mediante aplicaciones](./apps.md)
