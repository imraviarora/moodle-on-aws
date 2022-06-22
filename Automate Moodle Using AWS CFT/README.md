Setup Moodle Instance in AWS Using CloudFormation Template
=========


## About Moodle

Moodle is a learning platform designed to provide educators, administrators and learners with a single robust, secure and integrated system to create personalised learning environments.

Prerequisites:
```
Recommended hardware requirements (2 CPU, 2 GB Memory, 5GB Storage)
LAMP
Moodle Package
```

## Steps to set up moodle
-------------------------
1. Log into AWS Account and Make sure you're in N.Virginia Region
![AWSAccount](Snapshots/1AWSAccount.png)
3. Search for CloudFormation service and select it
4. 
The folder v3 contains the yaml specifications of the Voting App's services.

```
$ git clone https://github.com/imraviarora/voting-app-mca-final.git
$ cd voting-app-mca-final
$ kubectl create -f v3/
```

The voting application will be running at [http://localhost:32415](http://localhost:32415), and the results will be at [http://localhost:32414](http://localhost:32414).

OR

The voting application will be running at http://system-ip:32415, and the results will be at http://system-ip:32414.

## Stop this application
-------------------------

```
$ cd voting-app-mca-final
$ kubectl delete -f v3/
```


Architecture
-----

![Architecture diagram](architecture.png)

* A front-end web app in python which lets you vote between two options
* A Redis queue which collects new votes
* A .NET core worker which consumes votes and stores them in Postgres
* A Postgres database backed to store votes
* A Node.js webapp which shows the results of the voting in real time


Note
----

The voting application only accepts one vote per client. It does not register votes if a vote has already been submitted from a client.
