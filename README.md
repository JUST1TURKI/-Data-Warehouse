# Sparkify Database Project

## Purpose

The Sparkify database is designed to support analytical goals for the startup Sparkify. The primary purpose of the database is to store and analyze user activity data, specifically song plays. The analytical goals include understanding user behavior, analyzing song popularity, and gaining insights into various aspects of the user base.

## Database Schema Design and ETL Pipeline

The database schema follows a star schema, which is suitable for analytical queries. It includes the following tables:

- **Staging Tables:**
  - `staging_events`: Contains raw event data from users.
  - `staging_songs`: Contains raw song data.

- **Fact Table:**
  - `fact_song_play`: Contains information about each song play.

- **Dimension Tables:**
  - `dim_user`: Contains user information.
  - `dim_song`: Contains song details.
  - `dim_artist`: Contains artist details.
  - `dim_time`: Contains time-related information.

The ETL pipeline involves the following steps:

1. **Staging:**
   - Raw data is copied from Amazon S3 buckets (`LOG_DATA` and `SONG_DATA`) into staging tables (`staging_events` and `staging_songs`).

2. **Transformations:**
   - Data from staging tables is transformed and loaded into the fact and dimension tables using SQL queries.

3. **Load into Final Tables:**
   - The transformed data is loaded into the final fact and dimension tables.


