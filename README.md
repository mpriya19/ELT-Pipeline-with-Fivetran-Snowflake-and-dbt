# ELT Pipeline using Fivetran, Snowflake and dbt
This project implements an end-to-end ELT pipeline for e-commerce data using Fivetran, Snowflake and dbt.

Raw transactional data from Microsoft SQL Server is ingested into Snowflake using Fivetran, then transformed into analytics-ready models using dbt following the Medallion Architecture.

As visible in the diagram below, I followed an ELT (Extract, Load, Transform) approach, whereby data is first extracted and directly loaded into Snowflake DWH prior to its transformation with dbt.

<p align="center">
  <img src="https://raw.githubusercontent.com/mpriya19/ELT-Pipeline-with-Fivetran-Snowflake-and-dbt/main/assets/Architecture.png">
</p>

## Medallion Architecture
Data is logically organized in three different stages:
- **Bronze Layer**: Contains raw data. The table structures in this layer corresponds to the source system table structures.
  <p align="center">
    <img src="https://raw.githubusercontent.com/mpriya19/ELT-Pipeline-with-Fivetran-Snowflake-and-dbt/main/assets/Broze%20Layer%20ERD.jpg">
  </p>
  
- **Silver Layer**: This is where the data from the Bronze layer is merged, conformed and cleansed to standardize entities and relationships.

- **Gold Layer**: Data in this layer is typically organized into consumption-ready department-specific marts for BI/reporting purposes and uses de-normalized, dimensional data models (i.e. Inmon, Kimball).
  <p align="center">
    <img src="https://raw.githubusercontent.com/mpriya19/ELT-Pipeline-with-Fivetran-Snowflake-and-dbt/main/assets/Gold%20Layer%20ERD.jpg">
  </p>

The goal of such design pattern is to incrementally and progressively improve the structure and quality of data as it flows through each layer of the architecture.

## Key Learnings
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=postgresql&logoColor=white)  ![Snowflake](https://img.shields.io/badge/Snowflake-56B9EB?style=for-the-badge&logo=snowflake&logoColor=white)  ![dbt](https://img.shields.io/badge/dbt-FE752F?style=for-the-badge&logo=dbt&logoColor=white)  ![Medallion Architecture](https://img.shields.io/badge/Medallion%20Architecture-292929?style=for-the-badge)  ![Microsoft SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)  ![Fivetran](https://img.shields.io/badge/Fivetran-2176FF?style=for-the-badge&logo=fivetran&logoColor=white)  ![Dimensional Modeling](https://img.shields.io/badge/Dimensional%20Modeling-006400?style=for-the-badge)  ![SCD Type 1/2/4](https://img.shields.io/badge/SCD%20Type%201%2F2%2F4-008B8B?style=for-the-badge)
