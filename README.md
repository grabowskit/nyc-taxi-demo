# nyc-taxi-demo
NYC Taxi demo with Elasticsearch and Machine Learning

## Download Taxi data
Go to http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml and download the CSV file for Oct-Dec 2016 (Yellow cabs).

## Use Logstash to import into Elasticsearch

Change username and password in taxi.conf file in output section

Run Logstash with taxi.conf configuration file for each month

```
tail +2 yellow_tripdata_2016-09.csv | /logstash-6.3.1/bin/logstash -f taxi.conf
```

Go to Kibana, under Management create an index pattern called 'nyc-taxi-*'

## Import Kibana visualizations

In Kibana, Managmenet, Saved Objects, Import taxi.json file

## Import Machine Learning calendar

In Machine Learning, Go to Settings and import holiday.ics file to import 2016 holidays
