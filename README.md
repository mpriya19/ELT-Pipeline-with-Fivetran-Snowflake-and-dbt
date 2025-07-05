# ELT Pipeline using Fivetran, Snowflake and dbt

This project implements an end-to-end ELT pipeline for e-commerce data using Fivetran, Snowflake and dbt.

Raw transactional data from Microsoft SQL Server is ingested into Snowflake using Fivetran, then transformed into analytics-ready models using dbt following the Medallion Architecture.

As visible in the diagram below, I followed an ELT (Extract, Load, Transform) approach, whereby data is first extracted and directly loaded into Snowflake DWH prior to its transformation with dbt.

<p align="center">
  <img src="https://raw.githubusercontent.com/mpriya19/ELT-Pipeline-with-Fivetran-Snowflake-and-dbt/main/assets/Architecture%20Diagram.png">
</p>

## Medallion Architecture

Data is logically organized in three different stages:
- **Bronze Layer**: Contains raw data. The table structures in this layer corresponds to the source system table structures.
  <p align="center">
    <img src="https://github.com/mpriya19/assets/Broze Layer ERD.jpg">
  </p>
  
- **Silver Layer**: This is where the data from the Bronze layer is merged, conformed and cleansed to standardize entities and relationships.

- **Gold Layer**: Data in this layer is typically organized into consumption-ready department-specific marts for BI/reporting purposes and uses de-normalized, read-optimized data models (i.e. Inmon, Kimball).
  <p align="center">
    <img src="https://github.com/mpriya19/assets/Gold Layer ERD.jpg">
  </p>

The goal of such design pattern is to incrementally and progressively improve the structure and quality of data as it flows through each layer of the architecture.

Key transformation features include Type 1, Type 2 and Type 4 Slowly Changing Dimensions (SCDs), and dbt tests to ensure data quality.
All transformations are implemented in SQL using dbt, and the data warehouse is hosted on Snowflake.

## Conclusion

This project showcases a practical application of cloud-native tools to develop robust and scalable analytics workflows for modern data teams.
