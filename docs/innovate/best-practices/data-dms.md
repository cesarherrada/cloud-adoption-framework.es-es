---
title: 'Innovación en la nube: Data Migration Service'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Innovación en la nube: Data Migration Service'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 538cbc89fb592ecc19a5c25c42cf21231bfe05fe
ms.sourcegitcommit: 7ffb0427bba71177f92618b2f980e864b72742f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73047750"
---
# <a name="collect-data-through-the-migration-and-modernization-of-existing-data-sources"></a>Recopilación de datos mediante la migración y la modernización de los orígenes de datos existentes

A menudo, las empresas tienen una gran variedad de datos que se pueden [democratizar](../considerations/data.md). Cuando la hipótesis del cliente requiere el uso de los datos existentes para crear soluciones modernas, un primer paso es la migración y modernización de los datos para prepararse para las innovaciones e invenciones. A fin de alinear los trabajos de migración actuales dentro de un plan de adopción de la nube, la migración y la modernización pueden ejecutarse más fácilmente en la [metodología de migración](../../migrate/index.md).

## <a name="use-of-this-article"></a>Uso de este artículo

En este artículo se describe una serie de enfoques que se alinean con el proceso de migración, pero que se pueden alinear mejor con la cadena de herramientas de migración estándar. Durante el proceso de evaluación dentro de la metodología de migración, el equipo de adopción de la nube evaluaría el estado actual y el deseado para el futuro del recurso que se va a migrar. Cuando ese proceso forma parte de un trabajo de innovación, ambos equipos de adopción de la nube podrían usar este artículo para tomar esas decisiones.

## <a name="primary-toolset"></a>Conjunto de herramientas principal

Al migrar y modernizar los datos que se encuentran actualmente en el entorno local, la elección más común como herramienta de Azure es [Data Migration Service (DMS)](https://docs.microsoft.com/azure/dms) que forma parte de la cadena de herramientas [Azure Migrate](https://docs.microsoft.com/azure/migrate/migrate-services-overview) más amplia. En el caso de los orígenes de datos de SQL Server existentes, [Data Migration Assistant (DMA)](https://docs.microsoft.com/sql/dma/dma-overview) también podría proporcionar asistencia para evaluar y migrar un número menor de estructuras de datos.

Para admitir las migraciones de Oracle y NoSQL, también se puede usar [Data Migration Service (DMS)](https://docs.microsoft.com/azure/dms) para determinados tipos de origen en las bases de datos de destino, como Oracle para PostgreSQL o MongoDB para Cosmos DB. Es más común que los equipos de adopción aprovechen herramientas de terceros o scripts de migración personalizados para migrar a Cosmos DB, HDInsight u opciones de máquina virtual basadas en IaaS.

## <a name="considerations-and-guidance"></a>Consideraciones e instrucciones

Al aprovechar DMS para la migración y la modernización de los datos, es importante conocer la plataforma actual para hospedar los datos (origen), la versión y la plataforma y la versión futuras que mejor concuerden con la hipótesis del cliente (destino). A continuación, se muestra una lista de los pares de origen y de destino que se van a revisar con el equipo de migración. Cada uno incluye una elección de herramienta y un vínculo a una guía basada en estas consideraciones.

**Tipo de migración:** Con una migración sin conexión, el tiempo de inactividad de la aplicación se inicia cuando comienza la migración. Con una migración en línea, el tiempo de inactividad se limita al momento de la migración al final del proceso. Se recomienda que conozca cuál es el tiempo de inactividad aceptable para el negocio y pruebe una migración sin conexión para determinar si el tiempo de restauración lo cumple. Si no es así, realice una migración en línea.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server|Azure SQL Database|DMS|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-azure-sql)|
|SQL Server|Azure SQL Database|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-azure-sql-online)|
|SQL Server|Instancia administrada de Azure SQL Database|DMS|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-managed-instance)|
|SQL Server|Instancia administrada de Azure SQL Database|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-managed-instance-online)|
|RDS SQL Server|Azure SQL Database (o Instancia administrada)|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-rds-sql-server-azure-sql-and-managed-instance-online)|
|MySQL|Azure Database for MySQL|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-mysql-azure-mysql-online)|
|PostgreSQL|Azure Database for PostgreSQL|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-postgresql-azure-postgresql-online)|
|MondoDB|Mongo API de Azure Cosmos DB|DMS|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-mongodb-cosmos-db)|
|MongoDB|Mongo API de Azure Cosmos DB|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-mongodb-cosmos-db-online)|
|Oracle|Intervalo de opciones de PaaS e IaaS|Terceros o Azure Migrate|Varios|[Árbol de decisión](../../migrate/expanded-scope/data-oracle-migration.md)|
|Varias bases de datos NoSQL|Opciones de Cosmo DB o IaaS|Migraciones de procedimientos o Azure Migrate|Varios|[Árbol de decisión](../../migrate/expanded-scope/data-no-sql-migration.md)|
