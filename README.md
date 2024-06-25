---

# Introduction

You might have heard about data warehouses, data lakes, analysis cubes, Power BI (Business Intelligence) visuals and other reporting but are not exactly sure what they are and if your client needs them. This article will shed some much-needed light on each of the components in a reporting solution.

---

# Transactional Data Store (TDS/OLTP)
This is the Online Transaction Processing (OLTP) database that is optimized for transactions giving you high-volume fast inserts, updates & deletes of business data. It is used by an application for day-to-day operational tasks. It might contain your sales data, Customer Relationship Management (CRM), Enterprise Resource Planning (ERP), Supply Chain Management (SCM) or another line of business application for your company.

Key characteristics of an OLTP database include:

1. **Transaction Management**: These databases excel at managing transactions while ensuring data integrity and consistency. This is achieved through features like atomicity, consistency, isolation, and durability (ACID properties).
2. **Concurrent Access**: OLTP databases are designed to support multiple users or applications simultaneously, allowing many users to perform transactions concurrently without interfering with one another.
3. **Normalized Data Structures**: Data in TDS databases is typically organized using normalized structures to minimize redundancy and ensure efficient storage. This can help maintain data integrity but might involve more complex queries to retrieve data.
4. **Low Latency**: Transactional data store databases prioritize low-latency access to individual records, aiming to minimize response times for transactions.
5. **Indexing**: These databases often employ indexing techniques to optimize the retrieval of specific records and to facilitate efficient search operations.
6. **Small Transactions**: Transactions in OLTP databases are usually small-scale operations that involve relatively few records. This contrasts with OLAP (Online Analytical Processing) databases that focus on complex, analytical queries involving large datasets.
7. **Data Validation**: TDS databases enforce data validation and integrity constraints to ensure that only valid data is stored.
8. **Real-time Updates**: OLTP databases provide real-time updates to reflect changes in operational data as transactions occur.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/be34bc60-6ab0-4038-afcc-54c3df407a2b) -->
![Transactional Data Store](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/fc4d4fe1-7bec-4caf-b72a-70632a059e72)

---
# Operational Data Store (ODS)
An Operational Data Store (ODS) is a type of database or data storage system that is designed to store and manage real-time or near-real-time operational data from various sources within an organization. The primary purpose of an ODS is to provide a centralized repository for data that is used for day-to-day operational activities, reporting, and analysis.

Key characteristics of an ODS include:

1. **Real-time or Near-real-time Data**: It quickly gets the latest data for decisions.

2. **Combined Data**: It puts together data from different places so everyone sees the same info.

3. **Data Changes**: It fixes and organizes data to make sure it's right.

4. **Reports and Answers**: It helps with reports and quick questions about everyday tasks.

5. **Past Data**: It keeps a bit of old data to see trends and changes.

6. **Helps with Work**: It's useful for tasks like dealing with customers, orders, and inventory.

It's important to note that an ODS is distinct from a data warehouse. A data warehouse is designed for long-term storage, aggregation, and analysis of historical data from various sources, typically with a focus on business intelligence and decision support. In contrast, an ODS is oriented towards providing up-to-date information for day-to-day operations.

Overall, an ODS plays a crucial role in ensuring that an organization's operational activities have access to accurate and timely data, which is essential for effective decision-making and efficient business processes.

<!-- ![Operational Data Store (ODS)](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/501f4b3d-249f-4d34-9f4b-4707bd74d205) -->
![Operational Data Store](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/c849fcdf-22ea-4349-add4-4fcea5aded9f)
---


# Data Warehouse (DW)
This is the database that is optimized for analytical reporting giving you fast reads. The data is denormalized which means there is duplicate data stored in the tables. The duplicated data makes queries for reports and BI (Business Intelligence) visuals performant. The data from the TDS (Transactional Data Store) or ODS (Operational Data Store) is processed via ETL (Extract, Transform, Load) into the data warehouse. Data can also be imported from legacy systems via flat files. Data from modern APIs is fast becoming the standard for ingesting data into a data warehouse. Companies need to ensure they have a true data warehouse instead of a dumping ground for data with little modifications.

Companies need to make good decisions and to make good decisions requires good data. The best source for the data is a properly designed data warehouse and not a “reporting warehouse” or a “data swamp”.

Dimensions and Facts are created from the ingested data that are used in reporting. The Fact tables contain record data that can be aggregated (SUM, AVG, MIN, MAX) against. A Fact table has a specific grain that defines the level of detail for the records. The Dimension tables are used to slice the facts that answer the business staff’s data questions.

The dimensions and facts can be modeled in a Star or Snowflake schema. The Star Schema has one fact table in the middle surrounded by several associated dimensions tables. The Snowflake Schema adds additional dimensions that relate to another dimension.

Integration tables are for data ingestion. The integration tables are hidden from business users as they are only used for processing.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/79c494dd-0802-4293-8ad5-13ed59bd2766) -->
![Data Warehouse](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/88593da9-ba88-40c3-a17d-f878e52e732f)

---

# Data Lake, Data Lakehouse

A data lake is a centralized repository that stores your structured and unstructured data like CSV and Parquet files at any scale. Data in the data lake is initially stored as-is in its raw form without structuring or modeling the data files. There could be levels of refinement from raw to cleansed to application. The purpose of a data lake is to land your data in raw form for either data science uses or future dimensional modeling for more traditional data analysis.

The Data Lakehouse utilizes data structure and data management features on top of the Data Lake that are like what is found in a Data Warehouse.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/6331aff9-a120-41b2-b6b8-f1c233ae0ed8) -->
![Data Lake Data Lakehouse](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/6824fb31-bf46-4fba-abcb-c6efefa58542)

---

# Azure Synapse Analytics (Workspaces)

Azure Synapse is a unified data analytics platform that performs data integration, data exploration, data warehousing, big data, and machine learning in a single environment.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/3330a6ca-4992-426b-ae62-20ee3fcb2c93)-->
![Azure Synapse Analytics](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/303a50b4-4ea5-4dd5-904a-fe3e58d2559d)

Azure Synapse Workspace can be used with either a Dedicated SQL Pool or an ad-hoc Serverless SQL Pool. The Dedicated SQL Pool is an Azure Synapse instance.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/2aed1d5c-7100-4914-80c1-ccacdccc0926) -->
![Azure Synapse Analytics Pools](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/2909600b-3e88-41dc-87ea-c03fa9cfd09c)

Now, let’s say we want to edit our Power BI report. We can do this directly in Azure Synapse. Navigate to the Develop Hub blade and under the Power BI workspace Movie Analytics Reporting open Power BI reports. Here, we can see the Power BI report we just published.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/dcf47ef4-1ca4-4bf1-8373-70bd99f927a7) -->
![Azure Synapse Analytics Power BI](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/998e615f-ab30-4db8-8592-21e010ae27b2)

---

# Extract, Transform, Load (ETL or ELT)

The process of extracting, transforming, and loading data occurs at this stage. Data from the Transactional Data Store(s) is extracted from its system or an exported raw data file. The extracted data is stored in staging tables for processing into the data warehouse. Data transformations are performed against the raw source data to allow cleansing or reshaping of the data in flight.

The ETL process can be performed on-premises with SQL Server Integration Services ([SSIS](https://docs.microsoft.com/en-us/sql/integration-services/sql-server-integration-services)), or in Azure with Azure Data Factory ([ADF](https://azure.microsoft.com/en-us/services/data-factory/)), or [Azure Synapse Analytics](https://azure.microsoft.com/en-us/services/synapse-analytics).

SSIS & ADF Hybrid Solution:

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/882db707-227d-4365-ba5d-5a12cec85ef2) -->
![Extract Transform Load ADF](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/6850a48e-1fec-456c-9b3e-5d520b3642e1)

SSIS packages can also be run in ADF with "lift and shift". Moving your on-premises SSIS workloads to Azure has potential benefits of reduced operational costs, increased high availability and increased scalability.

**SSIS Works Well When**
- Your data is mostly or completely on-premises
- You already own SQL Server
- Your ETL packages runs throughout the day and not just a nightly job
- Your company has an investment is SSIS already

**ADF Works Well When**
- Most or all your data is in the cloud
- You don't have a sunk cost for SQL Server or are looking to migrate to the cloud
- Your ETL activity can be bulk loaded nightly or a few times during the day
- Your data is growing, and you want to pay for your current usage and not future usage

Example of SSIS Slowly Changing Dimension (SCD):
<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/35c446c8-373b-483c-b600-a9d2680170d0) -->
![Extract Transform Load ADF SCD](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/e464120a-8d19-4b1a-8140-aba226725939)

Example of ADF Slowly Changing Dimension (SCD):
<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/ef57bfd6-0800-4088-994a-2485ad12ac29) -->
![Extract Transform Load ADF SCD](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/dcea2d3a-805e-40d0-a6e5-f798d69f82d2)

---

# Microsoft Fabric

Microsoft Fabric is an all-in-one analytics solution for enterprises that covers everything from data movement to data science, Real-Time Analytics, and business intelligence (Power BI). It offers a comprehensive suite of services, including data lake, data engineering, and data integration, all in one place.

With Fabric, you don't need to piece together different services from multiple vendors. Instead, you can enjoy a highly integrated, end-to-end, and easy-to-use product that is designed to simplify your analytics needs.

The platform is built on a foundation of Software as a Service (SaaS), which takes simplicity and integration to a whole new level.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/cf0d42b8-5fc4-4a4a-9d18-c77e41c6c51b) -->
![Microsoft Fabric](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/e363283a-fec8-490f-9410-0ecd238d998f)

## OneLake and medallion lakehouse - the unification of  lakehouses
The Microsoft Fabric platform unifies the OneLake and lakehouse architecture across the enterprises.

OneLake
The data lake is the foundation on which all the Fabric services are built. Microsoft Fabric Lake is also known as OneLake. It's built into the Fabric service and provides a unified location to store all organizational data where the experiences operate.

Fabric brings together experiences such as Data Engineering, Data Factory, Data Science, Data Warehouse, Real-Time Analytics, and Power BI onto a shared SaaS foundation. This integration provides the following advantages:

- An extensive range of deeply integrated analytics in the industry.
- Shared experiences across experiences that are familiar and easy to learn.
- Developers can easily access and reuse all assets.
- A unified data lake that allows you to retain the data where it is while using your preferred analytics tools.
- Centralized administration and governance across all experiences.

![Microsoft Fabric OneLake Medallion Lakehouse Architecture](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/734106bc-5086-4ab8-8d7d-171227eec44e)

---

# Master Data Services (MDS)

Master data represents data about business entities for business transactions. These entities can be parties like individuals, customers, suppliers & employees. Other entities are products, ledgers, or cost centers. The goal is to conform the entities so they can be used across many fact tables in a DW.

When your company has data from ERP, CRM, SCM and Accounting systems these systems create data silos. Conforming the entities from the desperate systems allows you to have “one version of the truth” or a “golden version” of your data.

There are a few options to map these entities.

One option is a custom-built mapping web app.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/4d6bd8dd-e4d5-41cf-ba6d-da9f176e5bbb) -->
![Master Data Services Web App](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/d52f1ad7-79e5-4c1b-b55e-36480c389739)

Another option is Master Data Services (MDS) built into SQL Server Enterprise edition ($28k minimum license). Note: [Discontinued Master Data Services Features](https://learn.microsoft.com/en-us/sql/master-data-services/discontinued-master-data-services-features?view=sql-server-ver16) & [Deprecated Master Data Services Features](https://learn.microsoft.com/en-us/sql/master-data-services/deprecated-master-data-services-features?view=sql-server-ver16)

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/215b206b-00bb-482a-95a5-53201f0833f3) -->
![Master Data Services MDS](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/9db06058-c22a-4d97-8663-40e6c53ce073)

**Master Data Management/Service Alternative Options**

- [Master data management with Profisee and Azure Data Factory](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/data/profisee-master-data-management-data-factory)
- [Master data management with Azure and CluedIn](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/data/cluedin)
- [Data governance with Profisee and Microsoft Purview](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/data/profisee-master-data-management-purview)


---

# Analysis Cube (Cube)
An analysis cube is used to speed up queries with larger amounts of data. A cube is a multi-dimensional dataset that contains dimensions like locations, time, and sales data. If you use a business intelligence tool like Power BI, there is an option to import the data instead of a live query. When the data is imported it will create a cube within Power BI. This makes cubes not always necessary for data analytics for smaller data sets.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/08137670-fcb6-49f3-9dc0-d72a9d9fab5a) -->
![Analysis Cube Model](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/3eedcaf8-ef81-4cca-8e09-233295a07302)

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/bab34620-3728-418c-b32b-350f101c3483) -->
![Analysis Cube Cube](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/22d6953b-4bb9-40de-ad1b-8a1e1a9dba4d)

---

# Power BI Visual (Visuals)

Power BI (Business Intelligence) is one way to connect to the data warehouse or analysis cube to display insights that have been discovered in the data. Reports might have a single page with one visual or might have pages full of visuals. BI visuals give you the option to create Key Performance Indicators (KPI) to ensure your company is staying on track with its business goals.

These visuals have filters and interactive clickable elements in the visual to narrow down the data records. In the visuals below you can click the Midwest Sales Territory and all the other visuals on the page are sliced by that dimension.


<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/da395d83-551c-41f5-b63a-441947587844) -->
![Power BI](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/ac39535d-125b-452f-8f6a-5f97376e42f0)

---

# Power BI Mobile App (Power BI Mobile)

Power BI offers a set of mobile apps for iOS, Android, and Windows 10 mobile devices. In the mobile app, you connect to and interact with your cloud and on-premises data.

Business users can access their data anywhere, get notifications, annotate, and share, and dive deep into their data with powerful features for decision making on the go.

The screenshot below is displaying the same data from Power BI Report Server on a mobile phone.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/0021407b-4200-4d4c-b64f-ff26eccc9579)-->
![Power BI Mobile App](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/a11409f3-ef20-4db2-9cdd-6f2fe7e17271)


---

# Paginated Report (Paginated)

Normally there is enough report data that does not fit on one printed page, so the lines are split up to multiple pages (pagination). Paginated reports are pixel perfect and can be used for printing or formatted for complex reporting requirements like for regulatory documentation.

These report types have parameters that are developed during report authoring that allow the viewer to narrow down the returned data.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/2fb12e4b-016a-4497-a609-5597f6463c5a) -->
![Paginated Report](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/fb8685c5-5576-4018-ac50-a9ecbdd2f696)

---

# Power User Reports (Report Builder)

Report Builder is a tool for authoring paginated reports for business power users who prefer to work with a stand-alone software app instead of using a full development environment.

Business power users design a paginated report that creates a report definition. This report definition specifies what data to retrieve, where to get it, and how to display it. When they run the report, the report processor takes the report definition they have specified, retrieves the data, and combines it with the report layout to generate the report. They can preview their report in Report Builder. Then publish the report to a Reporting Services report server.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/5cd45186-8c80-4b6e-a636-9d500b511caf) -->
![Power User Reports](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/c83c1a84-717a-4c55-a76d-d71d8d287d04)

---

# Excel PivotTable (PivotTable)
An Excel PivotTable can be used to connect to the data warehouse or analysis cube to calculate, summarize, and analyze data. The PivotTable below is connected to a cube with customized measures in the PivotTable Fields panel on the right.

<!-- ![image](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/d05b1fe6-42bd-42df-a865-212d27590f44) -->
![Excel PivotTable](https://github.com/kevinmartintech/Data-Warehouse-Analysis-Cube-And-Reporting/assets/45496490/100ef5f7-88fe-48b3-8a2c-60de745e452d)
