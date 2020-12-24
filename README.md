# big-data-project-raspberry
# Hadoop Distributed Cluster on Raspberrypi
## Mathilde Angles Lambert Alexandre
## Cluster presentation
We made a cluster of 3 raspberrypi, we try to install a fully distributed system on the cluster with Hadoop, Yarn, Spark, Hbase, Hive, Kafka and Zookeeper.
The goal of this project is too reproduce the cluster we have seen in our big data ecosysteme course for a better comprhension of all the part of the hadoop ecosystem.
This was an hard task because there is compatibilities problem with the hadoop stack and the raspberry OS  architecture. But this was a great introduction for explore configurations files, linux server configuration.

All the Raspberrypi are remotely accessible via a VPN through SSH.
The static address of the raspberry and hostname are bellow :
 - pi1 192.168.1.23 user pi
 - pi2 192.168.1.24 user pi
 - pi3 192.168.1.25 user pi

For remotely access we use [piVpn](https://www.pivpn.io/) that is a recommended raspberry vpn service.
We gerenerate a .ovpn file that use for authentification and connection to the cluster.  Normaly you receive a mail with the .ovpn file and credential (subject : ece-big-data-project-lambert-angles-credentials)

For most of installation we follow offical doc and some tutorial, here some link's :
- [Hadoop+Spark](https://dev.to/awwsmm/building-a-raspberry-pi-hadoop-spark-cluster-8b2)
- [Hbase](http://www.ageekslab.com/bigdata/bigdata5/)
- [Zookeeper](http://www.ageekslab.com/bigdata/bigdata4/)

There is also a jupyter notebook server for coding with pysark.

The most disappointing point is that after all the installation we discover that raspberry os doesn't support aggregation with pyspark (e.g like sum()) so the initial idea to use the cluster for make small data analyse on velib open data was a little stop.
But we have write script who send velib data to kafka porducer. There is also script for read velib data and format it but we does'nt achieve to read data with pyspark kafka streaming.

This was a really great project because even if we failed on some point we learn a lot on how set up a distributed cluster with big data ecosystem. And we have pratice on the cluster. But the choice of the rapsberry laybe limited the utilisation (Hardware porbleme, lib probleme).

In the repository you can find some conf file of our cluster, a .basrch example.
All the installation are in /opt folder
Here some webUi of the cluster :
- [hdfs webUi](192.168.1.23:9870)
- [yarn webUi](192.168.1.23:8088)
- [jupyter server](192.168.1.23:8080)
- [Hbase webUi](192.168.1.23:16010)

It is not really easy to explain all of what we do in a readme but if you have question or you want to discuss about our project we can explain you what we do or answer your questions,
let notify us at : alexandre.lambert@edu.ece.fr
