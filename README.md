# ELK-dashboards
 - Project Description:
 
 This project helps in analyzing and visualizing various parameters of the dataset for used cars in germany. From this dataset, using analytics power of ELK stack, insights have been extracted to help us understand the raw data. Some of the insights gained from this small project are:
 1. Top 20 used-cars manufacturers
 2. The data and count of cars for the top manufacturers
 3. Average miles travelled by the car that are in the used-car lot listed by:
    - Top 10 used car manufacturers 
    - Fuel type - Gasoline, Diesel, LPG, CNG and Electric
 4. Top 5 used car manufacturer information broken down by:
    - Transmission type - Manual and Automatic
    - Fuel Type - Gasoline, Electric and Diesel
 5. Average miles driven by car broken down on:
     - Fuel Type - Gasoline, Diesel, LPG, CNG and Electric
     - Transmission type - Manual and automatic

- ELK Stack Installation: 
 
The versions used and installation websites have been mentioned below. For windows platform, ZIP files were downloaded to setup the required infrastructure.

Required dataset: Kaggle - used Czech republic cars
Link: https://www.kaggle.com/mirosval/personal-cars-classifieds

Elasticsearch: Version 5.4.1
Web URL: https://www.elastic.co/downloads/past-releases/elasticsearch-5-4-1

Kibana: Version 5.4.1
Web URL: https://www.elastic.co/downloads/past-releases/kibana-5-4-1

Logstash: Version Version 5.4.1
Web URL: https://www.elastic.co/downloads/past-releases/logstash-5-4-1

 - Project Setup:
 
This repository contains Elastisearch, Logstash and Kibana related analysis of big datasets. Dashboards have been created on local hosted Elasticsearch and Kibana servers on Windows platform. 
To navigate the project files, please see the project files structure below:

1. dashboard_images: Contains the visualizations prepared for the project summary. Please check the insights information above and filenames for correlation between tasks and images uploaded. 
2. configuration_files: This folder contains two files. Description has been mentioned below:
   - kibana.yml: Use this file to point to the respective Elasticsearch cluster or installation. Elasticsearch should be installed and running before this task is undertaken.
   - logstash.config: An extremely important file which tells logstash to import the data from data file in a particular schema defined by us. 
3. query_samples: This folder contains two files. These are general queries to get the count and search imported data through the index created using logstash.


 - Running the project:
 
 1. Make sure to download elastisearch first and unzip the file in the respective drive. 
 2. Run the elasticsearch from the location /elasticsearch-5.4.1/bin/elasticsearch.sh
 3. Download Kibana and unzip it in the respective folder.
 4. Now open the folder /kibana-5.4.1/config and make changes to "kibana.yml" file using the information posted above.
 5. Run Kibana from /kibana-5.4.1/bin/kibana.sh
 6. Download Logstash from above URL. Important thing here is to NOT keep elasticsearch and Logstash in the same folder directory.
 7. Prepare the configuration file. In this example, the file has been posted in the configuration_files folder.
 8. Download the dataset from the link mentioned above. Keep it in the same directory where you are making th configration file.
 9. Pass the required path of dataset and the schema. The configuration file has been uploaded in the configuration_files folder.
 10. Run the logstash job using:
     - bin/logstash -f logstash.config # the configuration file
 11. It might take some time to run the job as lot of rows are indexed.
 12. After the job has been completed for indexing data, run the queries in the query_samples folder for testing our indexed data.
 13. Lastly, create an index "cars*" in the Discover tab of Kibana.
 14. Start creating your dashboards.
