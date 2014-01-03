spring-xd-ec2
=============
This project simply allows you to deploy an XD cluster to ec2.  

Compiling
----------
* Once you have pulled the project from github go to the project root directory.
* To create an zip distribution execute the following: ./gradlew distZip
	* Once the compile is complete the distribution zip will be located in:
	 ${spring-xd-ec2}/build/distributions/spring-xd-ec2-1.0.zip

Installing
----------
1) Unzip spring-xd-ec2-1.0.zip

2) cd to the spring-ec2-1.0 directory

3) edit the config/xd-ec2.properties

	* set aws-access-key property to your AWS Access Key
	* set aws-secret-key property to your AWS Secret Key
	* set private-key-file to the location of your RSA private key and matching public-key-name
	* set the cluster-name property to the name you want to show up in the EC2 Instance console
	* set the user-name property to your name
	* set the description property, to define the purpose of this cluster.
	* set the xd-dist-url to be a specific .zip located in the one of the Spring repositories
	  * http://repo.spring.io/simple/libs-snapshot-local/org/springframework/xd/spring-xd/1.0.0.BUILD-SNAPSHOT/
	  * http://repo.spring.io/simple/libs-milestone-local/org/springframework/xd/spring-xd
	* To run multiple nodes, set multi-node=true and set the number-nodes key to the number of nodes you want to run.
        * Optionally set machine-size,region
	* Save 

Running
----------
1) From the spring-xd-ec2 directory run the install: ./bin/spring-xd-ec2
	* When the install is complete it will list the DNS name to your newly created instance. e.g.

	Admin Node Instance: ec2-54-205-186-126.compute-1.amazonaws.com has been created
	Container Node Instance: ec2-54-197-79-170.compute-1.amazonaws.com has been created


properties
----------

Using
----------

1) SSH into the boxes using the Public DNS names that were listed at the end of the install process, e.g.

$ ssh -i xd-key-pair.pem ubuntu@ec2-54-205-186-126.compute-1.amazonaws.com



