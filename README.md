# nyc-taxi-demo
NYC Taxi demo with Elasticsearch and Machine Learning

## Download Taxi data
Go to http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml and download the CSV file for Oct-Dec 2016 (Yellow cabs). To make it easier, use the script `download_raw_data.sh` to download those months (relies on you having `raw_data_urls.txt` local as well)

## Use Logstash to import into Elasticsearch

Change username and password in taxi.conf file in output section

Run Logstash with taxi.conf configuration file for each month - for example:

```
tail -n +2 /path/to/data/yellow_tripdata_2016-10.csv | /path/to/logstash-6.3.1/bin/logstash -f /path/to/taxi.conf
```

Go to Kibana, under Management create an index pattern called 'nyc-taxi-*'

## Import Kibana visualizations

In Kibana, Managmenet, Saved Objects, Import taxi.json file
