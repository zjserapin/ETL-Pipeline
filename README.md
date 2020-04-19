# ETL-Pipeline

This is a demo/walk through of the google qwiklab Building an IOT Analytics Pipeline on Google Cloud Platform

Full instructions and qwicklab here:https://www.qwiklabs.com/focuses/605?catalog_rank=%7B%22rank%22%3A8%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=5178336

The lab will go through how to:
  - Connect and manage MQTT-based devices
  - ingest a stream of info from cloud IoT core using Cloud Pub/Sub
  - process IoT data using Cloud Dataflow
  - analyze the IoT data
  
  
 1) First you need to enable the following api's:
    
    - Cloud IoT API, Cloud Pub/Sub API and Dataflow API
 
 2) Create a Cloud Pub/Sub Topic
 
    - Find Pub/Sub in navigation menu
    - go to topics
    - create and name a topic
    
 3) Big Query dataset
  
    -Navigate to BigQuery
    -Click on your project name and create dataset
    -Name the dataset and leave other fields blank
    -create a table, create appropriate fields and assign datatypes
    
 4) Create storage bucket
    
    -Navigate to Storage
    -Create bucket and make note of the name
    
  5) Set up Cloud Dataflow Pipeline
  
   - Navigate to Dataflow
   - Click "Create JOB from template"
   - enter jobname
   - choose "Cloud PubSub Topic to BigQuery" As the template
   - Specify the input topic as the Pub/Sub topic from step 2
   - Specify the output table as the dataset you created in BigQuery from step 3
   - Specify the temporary location as the Storage Bucket from step 4
   - If specifiying optional paramaters, make sure your machine type matches up with the VM instance you use or create in the next steps
   
   ![](https://github.com/zjserapin/ETL-Pipeline/blob/master/images/Screen%20Shot%202020-04-19%20at%209.39.19%20AM.png)
   
   - Run Job and check logs
   
   Step 6
   
   - Use or create a VM instance in GCP compute engine (Make sure machine type matches the one specified from dataflow!)
   - ssh into the instance create virtual enviornment, remove default GCP SDK installation and use curl command to install the latest version
   - Exit this SSH window and open a new one
   - source into new enviornment, verify your user account, update SDK components
   - install beta components and update Debian Linux package repositories
   - install required python software packages and clone in required git repositories
   - register the iot devices
   - create keypairs in the appropriate directory so IoT devices connect securely to Iot Core
   - Add simlated devices to your registry
   
   ![](https://github.com/zjserapin/ETL-Pipeline/blob/master/images/Screen%20Shot%202020-04-19%20at%2010.01.58%20AM.png)
   
   - Run these simulated devices and wait for results.
   
   ![](https://github.com/zjserapin/ETL-Pipeline/blob/master/images/Screen%20Shot%202020-04-19%20at%2010.05.19%20AM.png)
  
  Step 7
  
   - Once devices have finished running go back to BigQuery, run SQL Queries to pull data.
   - You should be able to see all of the data generated from these IoT devices
   - Then for further exploration/dashboard creation you can click into DataStudio!
   
   ![](https://github.com/zjserapin/ETL-Pipeline/blob/master/images/Screen%20Shot%202020-04-19%20at%2010.05.34%20AM.png)
   
 Check out the Demo video here:
   
