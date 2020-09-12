
## Translation code

```
## Lab 1: Getting Started with BigQuery
  #### Objectives

    ##### In this lab, you learn how to perform the following tasks:

    * Load data from Cloud Storage into BigQuery.
    * Perform a query on the data in BigQuery.

### Task 1: Load data from Cloud Storage into BigQuery
  
  1. In the Console, on the Navigation menu (Navigation menu) click BigQuery then click Done
  2. Create a new dataset within your project by selecting your project in the Resources section, then clicking on CREATE DATASET on the right
  3. In the Create Dataset dialog, for Dataset ID, type logdata.
  4. For Data location, select the continent closest to the region your project was created in. click Create dataset.
  5. Create a new table in the logdata to store the data from the CSV file.
  6. Click on Create Table. On the Create Table page, in the Source section:

For Create table from, choose select Google Cloud Storage, and in the field, type gs://cloud-training/gcpfci/access_log.csv.
Verify File format is set to CSV.
Note: When you have created a table previously, the Create from Previous Job option allows you to quickly use your settings to create similar tables.

   7. In the Destination section:
       * For Dataset name, leave logdata selected.
       * For Table name, type accesslog.
       * For Table name, type accesslog.
    8. Under Schema section, for Auto detect check the Schema and input Parameters.

    9. Accept the remaining default values and click Create Table.

    10. When the load job is complete, click logdata > accesslog.

### Task 2: Perform a query on the data using the BigQuery web UI
    
    1. In the Query editor window, type (or copy-and-paste) the following query:
    2. Because you told BigQuery to automatically discover the schema when you load the data, the hour of the day during which each web hit arrived is in a field called int_field_6.

      ###### Insert the below in the Query Box

       > select int64_field_6 as hour, count(*) as hitcount from logdata.accesslog
group by hour
order by hour
    3. Click Run and examine the results. At what time of day is the website busiest? When is it least busy?

### Task 3: Perform a query on the data using the bq command

    1. On the Google Cloud Platform Console, click Activate Cloud Shell Activate Cloud Shell then click Continue.

    2. At the Cloud Shell prompt, enter this command:
      > bq query "select string_field_10 as request, count(*) as requestcount from logdata.accesslog group by request order by requestcount desc"
  


      
