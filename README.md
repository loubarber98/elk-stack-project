# elk-stack-project
The purpose of the Elk stack is to set up a cloud monitoring system to show data in real time. The files have been tested in order to generate a live Elk deployment on Azure. The main purpose of this network is to expose a load-balanced and monitored instance of DVWA.The load balancers will protect the system from DDos attacks by shifting attack traffic. An advantage of the jump box is that the user gets access from a single node which can be secured and monitored.  The filebeat watches any information within the system that has been changed and when it was changed. The metricbeat takes the metrics and statistics that collects and ships them to the output you specify.

Elk Configuartion 
The anisble is used in order to automate the configuration of the Elk machine.Autommation speeds up deployment in order for the ELK machine to quickly create environments/applications, it cannot be done manully. The automation was used inorder to install the needed dockers and configure the ports. The ansible is used to allow the playbook to run. 

The playbook task

Access the ansible container in order to update the hosts by placing the Elk server VM IP under the group elkservers 
Then create the playbook to configure the elksever. The elksever has to be the hosts.
Once the playbook runs without any errors, SSh into the Elk server and run a docker ps to confirm that everything is running properly.
Then make sure that the Jumpbox IP is whitelisted and specify 5601 port to give you access to Kibanan.

Using the Playbook

Place the filebeat-playbook.yml file in /etc/ansible/ folder.
Then update the hosts file with the IP(s) of the ELK server and the web servers.
Run the playbook and go to kibana. Go to Logs > System Logs > Check data >Sytem logs dashboard to confirm that the installation worked. 

Commands to get Filebeat running 
Dowload Fileebat: curl -L -O https://artifacts.elastic.co.downloads.beat.filebeat/filebeat-7.4.0-amd64.deb


To install: dpkg -i filebeat-7.4.0-amd64.deb


To enable and configure they system module run: filebeat modules enable system
To setup run: filebeat setup

To start it run : service filebeat start



