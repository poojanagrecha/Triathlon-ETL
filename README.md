# Project: Triathlon ETL

## Background

This data analysis looks at data from two triathlon organizations, USA Triathlon (USAT) and National Senior Games Associations (NSGA). A senior triathlete is defined by the NSGA as someone 50+ years of age. While the layout of the data is different between the two sites, both contain information about total time taken to complete the triathlon, the sex of the triathlete, age data of the triathlete, and state data.


## Extract

We extracted data using splinter to open up a browser and go to the respective triathlon results main page. 

## Transform

Since the data is presented differently on each page, our group had to clean each dataset to provide commonality. 

## Load

Our database consists of four tables - three lookup tables for state data, organization data, and race metadata plus a table for race results. Below is the layout for the table:

- Race Table​ - this table is a lookup table containing the race metadata including the name and race of the date. Primary key is race_id, a serial integer automatically assigned by Postgres . Last updated will also be assigned by Postgres as the datetime of the last time the data was updated.

- Organization​ - this table is a lookup table which will identify the source of the race results. Primary key is organization_id, a serial integer automatically assigned by Postgres. Last updated will also be assigned by Postgres as the datetime of the last time the data was updated.

- State_Data​ - this table is a lookup table which will identify the State that the triathlete is from. Primary key is state_id, a serial integer automatically assigned by Postgres. Last updated will also be assigned by Postgres as the datetime of the last time the data was updated.

- Results​ - this is our main table which has information on the first name, last name, age range, gender, race time, and ranking. The table will have foreign keys for race_id, organization_id, and state_id.

![ERD Diagram](https://github.com/poojanagrecha/Triathlon-ETL/blob/master/Images/ETL_ERD.png)
