---
title: Aceleración de la migración con una migración de SQL
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aceleración de la migración con una migración de SQL
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 4af94af91874ac666f45a917eed003b3cf881c51
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72558614"
---
# <a name="accelerate-migration-with-a-sql-migration"></a>Aceleración de la migración con una migración de SQL

La migración de las instancias de SQL Server completas puede acelerar las labores de migración de las cargas de trabajo. La guía siguiente amplía el ámbito de la [guía de migración de Azure](../azure-migration-guide/index.md) mediante la migración de un servidor de SQL Server fuera de las labores de migración centradas en la carga de trabajo. Este enfoque puede inicializar la migración de varias cargas de trabajo con una sola migración de la plataforma de datos.

## <a name="general-scope-expansion"></a>Ampliación del ámbito general

La mayor parte del trabajo requerido en esta ampliación del ámbito se producirá durante los procesos de requisitos previos, evaluación, migración y optimización de un trabajo de migración.

<!-- markdownlint-disable MD026 -->

## <a name="is-this-expanded-scope-right-for-you"></a>¿Este ámbito ampliado es el adecuado para usted?

El enfoque recomendado descrito en la [guía de migración de Azure](../azure-migration-guide/index.md) es migrar cada estructura de datos junto con las cargas de trabajo asociadas como parte de un único trabajo de migración. El enfoque iterativo a la migración reduce la detección, la evaluación y otras tareas que pueden crear bloqueadores y ralentizar las devoluciones de valores empresariales.

Sin embargo, algunas estructuras de datos se pueden migrar de forma más eficaz mediante una migración de la plataforma de datos independiente. A continuación, se muestran algunos ejemplos que pueden conducir al uso de esta guía de ámbito expandida:

- **Fin de servicio:** Mover rápidamente una instancia de SQL Server para evitar los desafíos del fin de servicio puede justificar el uso de esta guía fuera de los trabajos de migración estándar.
- **Servicios de SQL Server:** La estructura de datos forma parte de una solución más amplia que requiere SQL Server que se ejecutan en una máquina virtual. Esto es común para las soluciones que aprovechan los servicios de SQL Server como SQL Server Reporting Services, SQL Server Integration Services o SQL Server Analysis Services.
- **Bases de datos de bajo uso y alta densidad:** La instancia de SQL Server tiene una elevada densidad de bases de datos. Cada una de esas bases de datos tiene pocos volúmenes de transacciones y requiere pocos recursos de proceso. Se deben tener en cuenta otras soluciones más modernas, pero un enfoque de IaaS podría dar lugar a un costo operativo significativamente menor.
- **Costo total de propiedad:** Cuando corresponda, se pueden aplicar las [Ventajas híbridas de Azure](https://azure.microsoft.com/pricing/hybrid-benefit) al precio de venta para crear el costo más bajo de propiedad para los servidores SQL Server. Esto es especialmente común para los clientes que hospedan SQL Server en escenarios de nube múltiple.
- **Acelerador de migración:** La migración mediante lift-and-shift de una instancia de SQL Server puede mover varias bases de datos en una iteración. En ocasiones, este enfoque permite que las futuras iteraciones se centren más específicamente en aplicaciones y máquinas virtuales, al migrar más cargas de trabajo en una sola iteración.
- **Migración de VMWare:** Una arquitectura local común incluye aplicaciones y máquinas virtuales en un host virtual y en bases de datos sin sistema operativo. Al migrar esta arquitectura común, la migración del host de VMWare al servicio de VMWare en Azure (AVS) se puede complementar con esta guía para migrar instancias de SQL Server completas para admitir esos hosts virtuales. Para obtener guías gratuitas, consulte [Migración de hosts de VMWare](./vmware-host.md).

Si ninguno de los criterios anteriores se aplica a esta migración, puede ser mejor continuar con el [proceso de migración estándar](../index.md). En el proceso estándar, las estructuras de datos se migran de forma iterativa junto con cada carga de trabajo.

Si esta guía se alinea con los criterios, continúe con esta guía de ámbito expandida como un trabajo en el [proceso de migración estándar](../index.md). Durante la fase de requisitos previos, el trabajo puede integrarse en el plan de adopción global.

## <a name="suggested-prerequisites"></a>Requisitos previos sugeridos

Antes de realizar una migración de SQL Server, comience con una expansión del **patrimonio digital** mediante la inclusión de un patrimonio de datos. El patrimonio de datos registra un inventario de los recursos de datos que se tienen en cuenta para la migración. En las tablas siguientes se describe un enfoque para registrar el patrimonio de datos.

### <a name="server-inventory"></a>Inventario de servidores

El siguiente es un ejemplo de un inventario de servidores para SQL Server:

|SQL Server|Propósito|Versión|[Importancia crítica](../../manage/considerations/criticality.md)|[Confidencialidad](../../govern/policy-compliance/data-classification.md)|Número de bases de datos|SSIS|SSRS|SSAS|Clúster|Número de nodos|
|---------|---------|---------|---------|---------|---------|---------|---------|
|sql-01|Aplicaciones básicas|2016|Crítica|Extremadamente confidencial|40|N/D|N/D|N/D|Sí|3|
|sql-02|Aplicaciones básicas|2016|Crítica|Extremadamente confidencial|40|N/D|N/D|N/D|Sí|3|
|sql-03|Aplicaciones básicas|2016|Crítica|Extremadamente confidencial|40|N/D|N/D|N/D|Sí|3|
|sql-04|BI|2012|Alto|XX|6|N/D|Confidencial|Sí, cubo multidimensional|Sin|1|
|sql-05|Integración|2008 R2|Bajo|General|20|Sí|N/D|N/D|Sin|1|

### <a name="database-inventory"></a>Inventario de base de datos

El siguiente es un ejemplo de un inventario de base de datos para uno de los servidores SQL anteriores:

|Server|Base de datos|[Importancia crítica](../../manage/considerations/criticality.md)|[Confidencialidad](../../govern/policy-compliance/data-classification.md)|Resultados de DMA|Corrección de DMA|Plataforma de destino|
|---------|---------|---------|---------|---------|---------|---------|
|sql-01|DB-1|Crítica|Extremadamente confidencial|Compatible|N/D|Azure SQL Database|
|sql-01|DB-2|Alto|Confidencial|Cambio de esquema requerido|Cambios implementados|Azure SQL Database|
|sql-01|DB-1|Alto|General|Compatible|N/D|Instancia administrada de Azure SQL|
|sql-01|DB-1|Bajo|Extremadamente confidencial|Cambio de esquema requerido|Cambios programados|Instancia administrada de Azure SQL|
|sql-01|DB-1|Crítica|General|Compatible|N/D|Instancia administrada de Azure SQL|
|sql-01|DB-2|Alto|Confidencial|Compatible|N/D|Azure SQL Database|

### <a name="integration-with-the-cloud-adoption-plan"></a>Integración con el plan de adopción de la nube

Una vez finalizada la detección, el plan puede incluirse en el [plan de adopción de la nube](../../plan/template.md). En el plan de adopción de la nube, agregue cada instancia de SQL Server que se va a migrar como una [carga de trabajo distinta](../../plan/workloads.md). Dentro de cada carga de trabajo, las bases de datos y los servicios (SSIS, SSAS, SSRS) se pueden agregar como [recursos](../../plan/workloads.md). Para agregar cargas de trabajo y recursos de forma masiva al plan de adopción, consulte [Agregar y editar elementos de trabajo con Excel](https://docs.microsoft.com/azure/devops/boards/backlogs/office/bulk-add-modify-work-items-excel?view=azure-devops).

Cuando las cargas de trabajo y los recursos se incluyen en el plan, el equipo puede continuar con un proceso de migración estándar mediante el plan de adopción para guiar los trabajos. Cuando el equipo de adopción se traslada a procesos de evaluación, migración y optimización, se deben tener en cuentan los siguientes cambios.

## <a name="assessment-process-changes"></a>Cambios en el proceso de evaluación

Si alguna base de datos del plan se puede migrar a una plataforma de datos como servicio (PaaS), utilice Data Migration Assistant para evaluar la compatibilidad de la base de datos seleccionada. Cuando la base de datos requiere conversiones de esquema, se recomienda que estas conversiones se completen como parte del proceso de evaluación para evitar interrupciones en la canalización de migración.

### <a name="suggested-action-during-the-assessment-process"></a>Acción sugerida durante el proceso de evaluación

En el caso de las bases de datos que se pueden migrar a una solución PaaS, se completarán las acciones siguientes durante el proceso de evaluación.

- **Evaluación con Data Migration Assistant:** Use Data Migration Assistant para detectar problemas de compatibilidad que pueden afectar a la funcionalidad de la base de datos en la instancia administrada de Azure SQL Database de destino, para recomendar mejoras en el rendimiento y la confiabilidad, y para trasladar el esquema, los datos y los objetos no contenidos desde el servidor de origen al servidor de destino. Para más información, consulte [Data Migration Assistant](/sql/dma/dma-overview).
- **Corrección y conversión:** En función de la salida de Data Migration Assistant, convierta el esquema de datos de origen para corregir los problemas de compatibilidad. Pruebe el esquema de datos convertido con las aplicaciones dependientes.

## <a name="migrate-process-changes"></a>Cambios en el proceso de migración

Durante la migración, hay varias opciones de enfoque y herramientas. Pero cada enfoque sigue un proceso sencillo: migrar esquema, datos y objetos. Sincronice los datos con el origen de datos de destino.

El destino y origen de la estructura de datos y los servicios pueden hacer que estos dos pasos sean bastante complicados. Consulte cada una de las siguientes secciones para comprender la mejor opción de herramientas en función de las decisiones de migración.

### <a name="suggested-action-during-the-migrate-process"></a>Acción sugerida durante el proceso de migración

La ruta de acceso sugerida para la migración y la sincronización utiliza una combinación de las tres herramientas siguientes. En las secciones siguientes se describen las opciones de migración y sincronización más complejas que permiten una variedad más amplia de soluciones de origen y de destino.

|Opción de migración|Propósito|
|---------|---------|
|[Azure Database Migration Service](/sql/dma/dma-overview)|Azure DMS admite migraciones en línea (tiempo de inactividad mínimo) y sin conexión (una vez) a escala en una instancia administrada de Azure SQL Database de SQL Server 2005, SQL Server 2008 y SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016 y SQL Server 2017.|
|[Replicación transaccional](/sql/relational-databases/replication/administration/enhance-transactional-replication-performance)|Se admite la replicación transaccional para una instancia administrada de Azure SQL Database para migraciones desde: SQL Server 2012 (SP2 CU8, SP3 o posterior), SQL Server 2014 (RTM CU10 o posterior o SP1 CU3 o posterior), SQL Server 2016, SQL Server 2017|
|[Cargas masiva](/sql/t-sql/statements/bulk-insert-transact-sql)|Use la carga masiva en una instancia administrada de Azure SQL Database para los datos almacenados en SQL Server 2005, SQL Server 2008 y SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016 y SQL Server 2017.|

### <a name="guidance-and-tutorials-for-suggested-migration-process"></a>Guías y tutoriales para el proceso de migración sugerido

La elección de la mejor guía para la migración con DMS depende de la plataforma de origen y de destino que elija. En la tabla siguiente se describen los tutoriales para cada uno de los enfoques estándar para migrar una base de datos SQL mediante DMS.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server|Azure SQL Database|DMS|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-azure-sql)|
|SQL Server|Azure SQL Database|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-azure-sql-online)|
|SQL Server|Instancia administrada de Azure SQL Database|DMS|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-managed-instance)|
|SQL Server|Instancia administrada de Azure SQL Database|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-managed-instance-online)|
|RDS SQL Server|Azure SQL Database (o Instancia administrada)|DMS|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-rds-sql-server-azure-sql-and-managed-instance-online)|

### <a name="guidance-and-tutorials-for-various-services-to-equivalent-paas-solutions"></a>Guías y tutoriales para varios servicios a soluciones PaaS equivalentes

Después de mover las bases de datos de un servidor SQL Server a DMS, el esquema y los datos se podrían hospedar en varias soluciones PaaS. Sin embargo, es posible que aún se estén ejecutando otros servicios necesarios en ese servidor. Los tres tutoriales siguientes le ayudarán a trasladar SSIS, SSAS y SSRS a servicios de PaaS equivalentes en Azure.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server Integration Services|Entorno de ejecución de integración de Data Factory|Azure Data Factory|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/data-factory/create-azure-ssis-integration-runtime)|
|SQL Server Analysis Services: modelo tabular|Azure Analysis Service|SSDT|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/analysis-services/analysis-services-deploy)|
|SQL Server Reporting Services|Power BI Report Server|Power BI|Sin conexión|[Tutorial](/power-bi/report-server/migrate-report-server)|

### <a name="guidance-and-tutorials-for-migration-from-sql-server-to-an-iaas-instance-of-sql-server"></a>Guías y tutoriales para la migración desde SQL Server a una instancia de IaaS de SQL Server

Después de migrar las bases de datos y los servicios a las instancias de PaaS, puede que todavía haya estructuras de datos y servicios que no sean compatibles con PaaS. Cuando las restricciones existentes impiden la migración de estructuras o servicios de datos, el siguiente tutorial puede ayudarle a migrar varios recursos de la cartera de datos a soluciones de IaaS de Azure.

Este enfoque se puede usar para migrar bases de datos en el servidor SQL Server u otros servicios que se ejecutan en el servidor SQL Server de origen.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server de instancia única|SQL Server en IaaS|Varía|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-migrate-sql)|

## <a name="optimization-process-changes"></a>Cambios en el proceso de optimización

Durante la optimización, cada estructura de datos, servicio o instancia de SQL Server se puede probar, optimizar y promocionar a producción. Este es el mayor impacto de la desviación de un modelo de migración por carga de trabajo.

Idealmente, las cargas de trabajo, las aplicaciones y las máquinas virtuales dependientes se migrarán dentro de la misma iteración que la instancia de SQL Server. Cuando se produce este escenario ideal, la carga de trabajo se puede probar junto con el origen de datos. Una vez realizada la prueba, la estructura de datos se puede promover a producción y el proceso de sincronización puede terminar.

Desafortunadamente, el cambio más importante en el proceso de optimización durante una migración no controlada por la carga de trabajo se produce cuando hay un intervalo de tiempo significativo entre la migración de la base de datos y la migración de la carga de trabajo. Cuando se migran varias bases de datos como parte de una migración SQL Server, dichas bases de datos pueden coexistir tanto en la nube como en el entorno local para varias iteraciones. Durante ese período, es necesario mantener la sincronización de datos hasta que se migren, prueben y promuevan esos recursos dependientes.

Hasta que se promuevan todas las cargas de trabajo dependientes, el equipo será responsable de admitir la sincronización de datos desde el sistema de origen al de destino. Esta sincronización consume ancho de banda de red, costos en la nube y, lo que es más importante, el tiempo de los usuarios. La correcta alineación del plan de adopción en la "carga de trabajo" de la migración de SQL Server y en todas las cargas de trabajo o aplicaciones dependientes reducirá esta sobrecarga costosa.

### <a name="suggested-action-during-the-optimization-process"></a>Acción sugerida durante el proceso de optimización

Durante los procesos de optimización, deben completarse las siguientes tareas en cada iteración hasta que todas las estructuras y servicios de datos se hayan promocionado a producción.

1. Valide la sincronización de los datos.
2. Pruebe cualquier aplicación migrada.
3. Optimice la aplicación y la estructura de datos para ajustar los costos.
4. Promueva las aplicaciones a producción.
5. Pruebe el tráfico local continuo en la base de datos local.
6. Finalice la sincronización de los datos promocionados a producción.
7. Finalice la base de datos de origen original.

Hasta que termine el paso 5, las bases de datos y la sincronización no se pueden finalizar. Hasta que todas las bases de datos de una instancia de SQL Server hayan pasado por los pasos 1-7, la instancia de SQL Server local debe tratarse como de producción y debe mantenerse toda la sincronización.

## <a name="next-steps"></a>Pasos siguientes

Vuelva a la [lista de comprobación del ámbito ampliado](./index.md) para asegurarse de que el método de migración está totalmente alineado.

> [!div class="nextstepaction"]
> [Lista de comprobación del ámbito ampliado](./index.md)
