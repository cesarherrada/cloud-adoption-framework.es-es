---
title: Herramientas de innovación para migrar datos
description: Más información sobre Azure Database Migration Service y otras herramientas que migran y modernizan los datos para prepararse para las invenciones e innovaciones de la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 1f6d7545814f51f79a45b619f73dab857ac582d3
ms.sourcegitcommit: 58ea417a7df3318e3d1a76d3807cc4e7e3976f52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "78891996"
---
# <a name="collect-data-through-the-migration-and-modernization-of-existing-data-sources"></a>Recopilación de datos mediante la migración y la modernización de los orígenes de datos existentes

A menudo, las empresas tienen diferentes tipos de datos existentes que pueden [democratizar](../considerations/data.md). Cuando una hipótesis de cliente requiere el uso de los datos existentes para crear soluciones modernas, un primer paso es la migración y modernización de los datos para prepararse para las innovaciones e invenciones. A fin de alinear los trabajos de migración existentes dentro de un plan de adopción de la nube, puede realizar la migración y la modernización más fácilmente en la [metodología de migración](../../migrate/index.md).

## <a name="use-of-this-article"></a>Uso de este artículo

En este artículo se describe una serie de enfoques que se alinean con el proceso de migración. Puede alinear mejor estos enfoques con la cadena de herramientas de migración estándar.

Durante el proceso de evaluación dentro de la metodología de migración, un equipo de adopción de la nube evalúa el estado actual y el deseado para el futuro del recurso migrado. Cuando ese proceso forma parte de un trabajo de innovación, ambos equipos de adopción de la nube pueden usar este artículo para ayudar con las evaluaciones.

## <a name="primary-toolset"></a>Conjunto de herramientas principal

Al migrar y modernizar datos locales, la elección de herramienta de Azure más común es [Azure Database Migration Service](https://docs.microsoft.com/azure/dms). Este servicio forma parte de la cadena de herramientas [Azure Migrate](https://docs.microsoft.com/azure/migrate/migrate-services-overview) más amplia. Para los orígenes de datos de SQL Server existentes, [Data Migration Assistant](https://docs.microsoft.com/sql/dma/dma-overview) puede ayudarle a evaluar y migrar un número reducido de estructuras de datos.

Para admitir las migraciones de Oracle y NoSQL, también puede usar [Database Migration Service](https://docs.microsoft.com/azure/dms) para determinados tipos de bases de datos de origen a destino. Entre los ejemplos se incluyen de Oracle a PostgreSQL y de MongoDB a Cosmos DB. Más comúnmente, los equipos de adopción usan herramientas de asociado o scripts personalizados para migrar a Azure Cosmos DB, Azure HDInsight o las opciones de máquina virtual basadas en infraestructura como servicio (IaaS).

## <a name="considerations-and-guidance"></a>Consideraciones e instrucciones

Al usar Azure Database Migration Service para la migración y la modernización de los datos, es importante comprender lo siguiente:

- La plataforma actual para hospedar el origen de datos.
- La versión actual.
- La plataforma y la versión futuras que mejor respaldan la hipótesis o el destino del cliente.

En la tabla siguiente se muestran los pares de origen y de destino que se van a revisar con el equipo de migración. Cada par incluye una elección de herramienta y un vínculo a una guía relacionada.

### <a name="migration-type"></a>Tipo de migración

Con una migración sin conexión, el tiempo de inactividad de la aplicación se inicia cuando comienza la migración. Con una migración en línea, el tiempo de inactividad se limita al momento de la migración al final del proceso.

Se recomienda que decida el tiempo de inactividad aceptable para el negocio y que pruebe una migración sin conexión. La finalidad es comprobar si el tiempo de restauración cumple el tiempo de inactividad aceptable. Si el tiempo de restauración no es aceptable, realice una migración en línea.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server|Azure SQL Database|Database Migration Service|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-azure-sql)|
|SQL Server|Azure SQL Database|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-azure-sql-online)|
|SQL Server|Instancia administrada de Azure SQL Database|Database Migration Service|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-managed-instance)|
|SQL Server|Instancia administrada de Azure SQL Database|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-managed-instance-online)|
|RDS SQL Server|Azure SQL Database o Instancia administrada de Azure SQL Database|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-rds-sql-server-azure-sql-and-managed-instance-online)|
|MySQL|Azure Database for MySQL|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-mysql-azure-mysql-online)|
|PostgreSQL|Azure Database for PostgreSQL|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-postgresql-azure-postgresql-online)|
|MongoDB|Mongo API de Azure Cosmos DB|Database Migration Service|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-mongodb-cosmos-db)|
|MongoDB|Mongo API de Azure Cosmos DB|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-mongodb-cosmos-db-online)|
