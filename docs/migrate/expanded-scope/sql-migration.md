---
title: Aceleración de la migración migrando una instancia de SQL Server
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: La migración de las instancias de SQL Server completas puede acelerar las labores de migración de las cargas de trabajo.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 444530a603d7d7e77bb71592a061486db835ea56
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73566896"
---
# <a name="accelerate-migration-by-migrating-an-instance-of-sql-server"></a>Aceleración de la migración migrando una instancia de SQL Server

La migración de las instancias de SQL Server completas puede acelerar las labores de migración de las cargas de trabajo. La guía siguiente amplía el ámbito de la [guía de migración de Azure](../azure-migration-guide/index.md) mediante la migración de una instancia de SQL Server fuera de las labores de migración centradas en la carga de trabajo. Este enfoque puede inicializar la migración de varias cargas de trabajo con una sola migración de la plataforma de datos. La mayor parte del trabajo requerido en esta ampliación del ámbito se produce durante los procesos de requisitos previos, evaluación, migración y optimización de un trabajo de migración.

<!-- markdownlint-disable MD026 -->

## <a name="is-this-expanded-scope-right-for-you"></a>¿Este ámbito ampliado es el adecuado para usted?

El enfoque recomendado descrito en la [guía de migración de Azure](../azure-migration-guide/index.md) es migrar cada estructura de datos junto con las cargas de trabajo asociadas como parte de un único trabajo de migración. El enfoque iterativo a la migración reduce la detección, la evaluación y otras tareas que pueden crear bloqueadores y ralentizar las devoluciones de valores empresariales.

Sin embargo, algunas estructuras de datos se pueden migrar de forma más eficaz mediante una migración de la plataforma de datos independiente. Estos son algunos ejemplos:

- **Fin de servicio:** Mover rápidamente una instancia de SQL Server para evitar los desafíos del fin de servicio puede justificar el uso de esta guía fuera de los trabajos de migración estándar.
- **Servicios de SQL Server:** La estructura de datos forma parte de una solución más amplia que requiere SQL Server que se ejecutan en una máquina virtual. Esto es común para las soluciones que emplean los servicios de SQL Server como SQL Server Reporting Services, SQL Server Integration Services o SQL Server Analysis Services.
- **Bases de datos de bajo uso y alta densidad:** La instancia de SQL Server tiene una elevada densidad de bases de datos. Cada una de esas bases de datos tiene pocos volúmenes de transacciones y requiere pocos recursos de proceso. Se deben tener en cuenta otras soluciones más modernas, pero un enfoque de infraestructura como servicio (IaaS) podría dar lugar a un costo operativo significativamente menor.
- **Costo total de propiedad:** Cuando corresponda, puede aplicar las [Ventajas híbridas de Azure](https://azure.microsoft.com/pricing/hybrid-benefit) al precio de venta para crear el costo más bajo de propiedad para las instancias de SQL Server. Esto es especialmente común para los clientes que hospedan SQL Server en escenarios de nube múltiple.
- **Acelerador de migración:** La migración mediante lift-and-shift de una instancia de SQL Server puede mover varias bases de datos en una iteración. En ocasiones, este enfoque permite que las futuras iteraciones se centren más específicamente en aplicaciones y máquinas virtuales, lo que significa que puede migrar más cargas de trabajo en una sola iteración.
- **Migración de VMware:** Una arquitectura local común incluye aplicaciones y máquinas virtuales en un host virtual y en bases de datos sin sistema operativo. En este escenario, puede migrar instancias de SQL Server completas para dar respaldo a la migración del host de VMware al servicio de VMware en Azure. Para más información, consulte [Migración de hosts de VMware](./vmware-host.md).

Si ninguno de los criterios anteriores se aplica a esta migración, puede que sea mejor continuar con el [proceso de migración estándar](../index.md). En el proceso estándar, las estructuras de datos se migran de forma iterativa junto con cada carga de trabajo.

Si esta guía se alinea con los criterios, continúe con esta guía de ámbito expandida como un trabajo en el [proceso de migración estándar](../index.md). Durante la fase de requisitos previos, el esfuerzo puede integrarse en el plan de adopción global.

## <a name="suggested-prerequisites"></a>Requisitos previos sugeridos

Antes de realizar una migración de SQL Server, comience con una expansión del patrimonio digital mediante la inclusión de un patrimonio de datos. El patrimonio de datos registra un inventario de los recursos de datos que se tienen en cuenta para la migración. En las tablas siguientes se describe un enfoque para registrar el patrimonio de datos.

### <a name="server-inventory"></a>Inventario de servidores

El siguiente es un ejemplo de un inventario de servidores:

|SQL Server|Propósito|Versión|[Importancia crítica](../../manage/considerations/criticality.md)|[Confidencialidad](../../govern/policy-compliance/data-classification.md)|Número de bases de datos|SSIS|SSRS|SSAS|Clúster|Número de nodos|
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|sql-01|Aplicaciones básicas|2016|Críticas|Extremadamente confidencial|40|N/D|N/D|N/D|Sí|3|
|sql-02|Aplicaciones básicas|2016|Críticas|Extremadamente confidencial|40|N/D|N/D|N/D|Sí|3|
|sql-03|Aplicaciones básicas|2016|Críticas|Extremadamente confidencial|40|N/D|N/D|N/D|Sí|3|
|sql-04|BI|2012|Alto|XX|6|N/D|Confidencial|Sí, cubo multidimensional|Sin|1|
|sql-05|Integración|2008 R2|Bajo|General|20|Sí|N/D|N/D|Sin|1|

### <a name="database-inventory"></a>Inventario de base de datos

El siguiente es un ejemplo de un inventario de base de datos para uno de los servidores anteriores:

|Server|Base de datos|[Importancia crítica](../../manage/considerations/criticality.md)|[Confidencialidad](../../govern/policy-compliance/data-classification.md)|Resultados de Data Migration Assistant (DMA)|Corrección de DMA|Plataforma de destino|
|---------|---------|---------|---------|---------|---------|---------|
|sql-01|DB-1|Críticas|Extremadamente confidencial|Compatible|N/D|Azure SQL Database|
|sql-01|DB-2|Alto|Confidencial|Cambio de esquema requerido|Cambios implementados|Azure SQL Database|
|sql-01|DB-1|Alto|General|Compatible|N/D|Instancia administrada de Azure SQL|
|sql-01|DB-1|Bajo|Extremadamente confidencial|Cambio de esquema requerido|Cambios programados|Instancia administrada de Azure SQL|
|sql-01|DB-1|Críticas|General|Compatible|N/D|Instancia administrada de Azure SQL|
|sql-01|DB-2|Alto|Confidencial|Compatible|N/D|Azure SQL Database|

### <a name="integration-with-the-cloud-adoption-plan"></a>Integración con el plan de adopción de la nube

Una vez finalizado este proceso de detección, puede incluirlo en el [plan de adopción de la nube](../../plan/template.md). En el plan de adopción de la nube, agregue cada instancia de SQL Server que se va a migrar como una [carga de trabajo distinta](../../plan/workloads.md). Dentro de cada carga de trabajo, las bases de datos y los servicios (SSIS, SSAS, SSRS) se pueden agregar como [recursos](../../plan/workloads.md). Para agregar cargas de trabajo y recursos de forma masiva al plan de adopción, consulte [Agregar y editar elementos de trabajo con Excel](https://docs.microsoft.com/azure/devops/boards/backlogs/office/bulk-add-modify-work-items-excel?view=azure-devops).

Después de que las cargas de trabajo y los recursos se hayan incluido en el plan, usted y su equipo pueden continuar con un proceso de migración estándar mediante el plan de adopción. Cuando el equipo de adopción se traslada a procesos de evaluación, migración y optimización, debe tener en cuenta los cambios que se analizan en las secciones siguientes.

## <a name="assessment-process-changes"></a>Cambios en el proceso de evaluación

Si alguna base de datos del plan se puede migrar a una plataforma de datos como servicio (PaaS), utilice Data Migration Assistant para evaluar la compatibilidad de la base de datos seleccionada. Cuando la base de datos requiere conversiones de esquema, debe completar estas conversiones como parte del proceso de evaluación para evitar interrupciones en la canalización de migración.

### <a name="suggested-action-during-the-assessment-process"></a>Acción sugerida durante el proceso de evaluación

En el caso de las bases de datos que se pueden migrar a una solución PaaS, se completarán las acciones siguientes durante el proceso de evaluación.

- **Evaluación con DMA:** Use Data Migration Assistant para detectar problemas de compatibilidad que pueden afectar a la funcionalidad de la base datos de la Instancia administrada de Azure SQL Database de destino. Use DMA para recomendar mejoras de rendimiento y confiabilidad y para migrar el esquema, los datos y objetos no contenidos desde el servidor de origen al de destino. Para más información, consulte [Data Migration Assistant](https://docs.microsoft.com/sql/dma/dma-overview).
- **Corrección y conversión:** En función de la salida de Data Migration Assistant, convierta el esquema de datos de origen para corregir los problemas de compatibilidad. Pruebe el esquema de datos convertido con las aplicaciones dependientes.

## <a name="migrate-process-changes"></a>Cambios en el proceso de migración

Durante la migración, puede elegir entre muchas herramientas y enfoques distintos. Pero cada enfoque sigue un proceso sencillo: migrar esquema, datos y objetos. Posteriormente, sincronice los datos con el origen de datos de destino.

El destino y origen de la estructura de datos y los servicios pueden hacer que estos dos pasos sean bastante complicados. Las siguientes secciones le ayudarán a conocer la mejor opción de herramientas en función de las decisiones de migración.

### <a name="suggested-action-during-the-migrate-process"></a>Acción sugerida durante el proceso de migración

La ruta de acceso sugerida para la migración y la sincronización utiliza una combinación de las tres herramientas siguientes. En las secciones siguientes se describen las opciones de migración y sincronización más complejas que permiten una variedad más amplia de soluciones de origen y de destino.

|Opción de migración|Propósito|
|---------|---------|
|[Azure Database Migration Service](https://docs.microsoft.com/sql/dma/dma-overview)|Admite migraciones en línea (con un tiempo de inactividad mínimo) y sin conexión (una vez) a escala en una instancia administrada de Azure SQL Database. Admite la migración desde: SQL Server 2005, SQL Server 2008 y SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016 y SQL Server 2017.|
|[Replicación transaccional](https://docs.microsoft.com/sql/relational-databases/replication/administration/enhance-transactional-replication-performance)|Se admite la replicación transaccional para una instancia administrada de Azure SQL Database para migraciones desde: SQL Server 2012 (SP2 CU8, SP3 o posterior), SQL Server 2014 (RTM CU10 o posterior o SP1 CU3 o posterior), SQL Server 2016, SQL Server 2017.|
|[Cargas masiva](https://docs.microsoft.com/sql/t-sql/statements/bulk-insert-transact-sql)|Use la carga masiva en una instancia administrada de Azure SQL Database para los datos almacenados en: SQL Server 2005, SQL Server 2008 y SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016 y SQL Server 2017.|

### <a name="guidance-and-tutorials-for-suggested-migration-process"></a>Guías y tutoriales para el proceso de migración sugerido

La elección de la mejor guía para la migración con Database Migration Service depende de la plataforma de origen y de destino que elija. La tabla siguiente se vincula a los tutoriales de cada uno de los enfoques estándar para migrar una base de datos SQL mediante Database Migration Service.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server|Azure SQL Database|Database Migration Service|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-azure-sql)|
|SQL Server|Azure SQL Database|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-azure-sql-online)|
|SQL Server|Instancia administrada de Azure SQL Database|Database Migration Service|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-managed-instance)|
|SQL Server|Instancia administrada de Azure SQL Database|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-sql-server-managed-instance-online)|
|RDS SQL Server|Azure SQL Database (o instancia administrada)|Database Migration Service|En línea|[Tutorial](https://docs.microsoft.com/azure/dms/tutorial-rds-sql-server-azure-sql-and-managed-instance-online)|

### <a name="guidance-and-tutorials-for-various-services-to-equivalent-paas-solutions"></a>Guías y tutoriales para varios servicios a soluciones PaaS equivalentes

Después de mover las bases de datos de una instancia de SQL Server a Database Migration Service, el esquema y los datos se podrían rehospedar en varias soluciones PaaS. Sin embargo, es posible que aún se estén ejecutando otros servicios necesarios en ese servidor. Los tres tutoriales siguientes le ayudarán a trasladar SSIS, SSAS y SSRS a servicios de PaaS equivalentes en Azure.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server Integration Services|Entorno de ejecución de integración de Azure Data Factory|Azure Data Factory|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/data-factory/create-azure-ssis-integration-runtime)|
|SQL Server Analysis Services: modelo tabular|Azure Analysis Services|SQL Server Data Tools|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/analysis-services/analysis-services-deploy)|
|SQL Server Reporting Services|Power BI Report Server|Power BI|Sin conexión|[Tutorial](https://docs.microsoft.com/power-bi/report-server/migrate-report-server)|

### <a name="guidance-and-tutorials-for-migration-from-sql-server-to-an-iaas-instance-of-sql-server"></a>Guías y tutoriales para la migración desde SQL Server a una instancia de IaaS de SQL Server

Después de migrar las bases de datos y los servicios a las instancias de PaaS, puede que todavía haya estructuras de datos y servicios que no sean compatibles con PaaS. Cuando las restricciones existentes impiden la migración de estructuras o servicios de datos, el siguiente tutorial puede ayudarle a migrar varios recursos de la cartera de datos a soluciones de IaaS de Azure.

Utilice este enfoque para migrar bases de datos u otros servicios en la instancia de SQL Server.

|Source  |Destino  |Herramienta  |Tipo de migración  |Guía  |
|---------|---------|---------|---------|---------|
|SQL Server de instancia única|SQL Server en IaaS|Varía|Sin conexión|[Tutorial](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-migrate-sql)|

## <a name="optimization-process-changes"></a>Cambios en el proceso de optimización

Durante la optimización, cada estructura de datos, servicio o instancia de SQL Server se puede probar, optimizar y promocionar a producción. Este es el mayor impacto de la desviación de un modelo de migración por carga de trabajo.

Idealmente, las cargas de trabajo, las aplicaciones y las máquinas virtuales dependientes se migran dentro de la misma iteración que la instancia de SQL Server. Cuando se produce este escenario ideal, la carga de trabajo se puede probar junto con el origen de datos. Después de realizar las pruebas, puede promocionar la estructura de datos a producción y finalizar el proceso de sincronización.

Ahora, considere un escenario en el que hay un intervalo de tiempo significativo entre la migración de la base de datos y la de la carga de trabajo. Desafortunadamente, este puede constituir el mayor cambio en el proceso de optimización durante una migración no controlada por la carga de trabajo. Cuando se migran varias bases de datos como parte de una migración SQL Server, esas bases de datos pueden coexistir tanto en la nube como en el entorno local para varias iteraciones. Durante ese período, debe mantener la sincronización de datos hasta que se migren, prueben y promuevan esos recursos dependientes.

Hasta que se promuevan todas las cargas de trabajo dependientes, usted y el equipo serán responsables de dar respaldo a la sincronización de datos desde el sistema de origen al de destino. Esta sincronización consume ancho de banda de red, costos en la nube y, lo que es más importante, el tiempo de los usuarios. La correcta alineación del plan de adopción en la carga de trabajo de la migración de SQL Server y en todas las cargas de trabajo o aplicaciones dependientes reducirá esta sobrecarga costosa.

### <a name="suggested-action-during-the-optimization-process"></a>Acción sugerida durante el proceso de optimización

Durante los procesos de optimización, deben completarse las siguientes tareas en cada iteración hasta que todas las estructuras y servicios de datos se hayan promocionado a producción.

1. Valide la sincronización de los datos.
2. Pruebe cualquier aplicación migrada.
3. Optimice la aplicación y la estructura de datos para ajustar los costos.
4. Promueva las aplicaciones a producción.
5. Pruebe el tráfico local continuo en la base de datos local.
6. Finalice la sincronización de los datos promocionados a producción.
7. Finalice la base de datos de origen original.

Hasta que termine el paso 5, las bases de datos y la sincronización no se pueden finalizar. Hasta que todas las bases de datos de una instancia de SQL Server hayan pasado por todos los siete pasos, debe tratar la instancia local de SQL Server como de producción. Se debe mantener toda la sincronización.

## <a name="next-steps"></a>Pasos siguientes

Vuelva a la [lista de comprobación del ámbito ampliado](./index.md) para asegurarse de que el método de migración está totalmente alineado.

> [!div class="nextstepaction"]
> [Lista de comprobación del ámbito ampliado](./index.md)
