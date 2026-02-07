# Rank Flow AI 
Rank flow is an application with the following components ;
* SQL Command files for DDL and Seed values. Some tables are created in PostgreSQL, and some tables are created in Google BigQuery.
* Backend written in Golang for multiple binaries (main Files), one exe file is http backend server, others are standalone micro services. Backend generates some binary data files and stores them in GCS buckets. Backend is  using GCP services; it will also be compiled for equivalent services in AWS to build an AWS version 
* Frontend is written in Angular language, build generates 3 static files. Index.html, style.css, and application.js. These files will be located in a bucket and served from there. Frontend is independent of the platform
