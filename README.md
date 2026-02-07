# Rank Flow AI 
Rank flow is an application with the following components ;
* SQL Command files for DDL and Seed values.
   - basis_pgsql.sql : DDL for application setup tables for users, roles, profiles, application menu and items, rest api tables and relations, domain options and constants for lookup values. For PostGreSQL
   - basis_seed.sql : Seed values for application setup
   - bbp_pgsql.sql: DDL for business plan subscription plans and quota management tables
   - bbp_seed.sql : Seed values for bbp tables
   - mmm_pgsql : DDL for Rank Flow application OLTP tables for PostGreSQL
   - mmm_bq.sql : DDL for Rank Flow application OLAP (analytic) tables for Google BigQuery
   - mmm_seed.sql : Seed values for Rank Flow tables
* Backend written in Golang for multiple binaries:
  Backend is developed for using GCP services in initial deployments. It will also be compiled for equivalent services in AWS to build an AWS version.
   - http : Backend HTTP server for REST API services
   - crawker : Microservice for crawling business partner and competitor pages
   - reviewer : Microservice for retrieving GBP reviews and citation, AI agent for replying the reviews
   - Ranker : Microservice for ranking business partner pages
   - audit : Misroservice for running SEO/GEO audits on the collected data, report and create action items
   - generator : AI agent for generating BLOG or video content. Generated content are stored in GCS buckets
   - publisher : Microservice for publishing the generated content to various social media platforms or CMS applications.
* Frontend is written in Angular language
   - When build, the frontend is compiled into 3 static files: index.html, style.css, and appbundle.js. These files will be located in a bucket and served from there. Frontend interacts with the backend and is independent from the cloud or database platform.
