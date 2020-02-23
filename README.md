# Tado Configuration for NodeRed

I discovered NodeRed and I decided to create a configuration to:
* extract data from Tado smart thermostat solution
* distill the datastream
* publish the interesting bits over MQTT
* pull MQTT into prometheus
* graph everything in grafana
* run everything on Kubernetes

Currently the cluster is ready and available, and it's easy for you also to set one up using K3Sroll https://github.com/embcla/k3sroll

A streamlined Vagrant configuration file to spin up a variable size cluster with K3S.
On top of the cluster then need to run prometheus, grafana and nodered.

# NodeRed
Added a JSON flow definition to extract data for each room from Tado, parse it, clean it and retransmit it over MQTT.
MQTT stream will then be routed through prometheus and grafana for analysis and graphing
![NodeRed Tado Flow](/Tado%20NodeRed%20Flow.PNG)
