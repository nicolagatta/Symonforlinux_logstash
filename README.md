# Sysmon for Linux, Filebeat and Logstash

I wanted to try out sysmon for linux and send logs to an existing ELK stack I already use to store logs from windows, Linux servers, switches and vmware.

After some digging I decided to create a separate pipeline dedicated to sysmon for Linux and filebeat from

The schema is basically 
sysmon sends events to rsyslogd --> rsyslogd stores them in a dedicated file /var/log/sysmon.log --> Filebeat ships to Logstash via network (SSL)
Logstash has the unfortunate task to parse the XML and compile fields to send to Elasticsearch.

The difficult part was to setup the logstash filter.


  
