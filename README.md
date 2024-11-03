# **ELK-Project**

## **Overview**
This Project using ELK components to collect, process and visualize system data.

## **Thecnologies Used**
* Logstash
* Elasticsearch
* Kibana

## **Instructions**
1. Set up an Ubuntu server machine.
2. Install Elasticsearch:
   "wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.15.3-amd64.deb"
   "sudo dpkg -i https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.15.3-amd64.deb"
   "sudo systemctl start elasticsearch"
   "sudo systemctl enable elasticsearch"
4. Install and set Logstash:
   "wget https://artifacts.elastic.co/downloads/logstash/logstash-8.15.3-amd64.deb"
   "sudo dpkg -i https://artifacts.elastic.co/downloads/logstash/logstash-8.15.3-amd64.deb"
   Create logstash configuration file in /etc/logstash/conf.d/, use the file in this repository.
   "sudo usermod -aG adm logstash"
   "sudo systemctl start logstash"
   "sudo systemctl enable logstash"
   In /etc/logstash/logstash.yml configure the logstash log path:
   "path.logs: /var/log/logstash.log"
   For dedicated place for logs and to prevent a situation of loops in the syslog, where every operatioanl message of Logstash is written to syslog, and Logstash read those entries as new logs so he writes continiusly.
6. Install Kibana:
   "wget https://artifacts.elastic.co/downloads/kibana/kibana-8.15.3-amd64.deb"
   "sudo dpkg -i https://artifacts.elastic.co/downloads/kibana/kibana-8.15.3-amd64.deb"
   "sudo systemctl start kibana"
   "sudo systemctl enable kibana"
7. Test and access the Stack:
   For Elasticsearch go to http://localhost:9200
   For Kibana go to http://localhost:5601
8. Create a data view:
   Go to Stack management > Data vies
   click Create data views and put the index pattern
9. Create visualization:
   From Kibana go to Visualize Libary, then click Create visualization.
   Here you can choose what visualization you want, for example Lens, then you can filter it for example type om the search bar "message.keyword *permission*" to get filter all the logs conatain the word permission.
