# Prerequisites
*   Access to RDS
*   Access to MongoDB Atlas
*   [Create a Confluent Cloud account](https://www.confluent.io/confluent-cloud/tryfree/)
*   [Install mongosh](https://www.mongodb.com/docs/mongodb-shell/install/) 
*   Ability to execute *curl* command. If curl is not available, please install it
*   [Install Confluent CLI](https://docs.confluent.io/confluent-cli/current/install.html#install-confluent-cli)


# Architecture

<br>


---


# Setup Clusters

###   `1.  Sign-in using - https://confluent.cloud/login`


---


###   `2.  Create a new environment`


![e1](images/environment-1.png)

![e2](images/environment-2.png)

---

###   `3.  Enable Schema Registry - Begin Configuration ->  Essentials Package`

![s1](images/sr-1.png)

![s2](images/sr-2.png)

---

###   `4.  Now Create The Kafka Cluster`

![c1](images/cluster-1.png)

![c12](images/cluster-12.png)

![c13](images/cluster-13.png)

![c14](images/cluster-14.png)

![c15](images/cluster-5.png)

---


###   `4.  Now Create The KSQLDB Cluster`

![k1](images/ksql-1.png)

![k2](images/ksql-2.png)

![k3](images/ksql-3.png)

![k4](images/ksql-4.png)

![k5](images/ksql-5.png)

---

###   `5.  Create The MySQL CDC Connector`
*   Host name - globestreamingday.cqzooevua9cx.ap-southeast-1.rds.amazonaws.com
*   Port - 3306
*   DB Name - cdcdb
*   User Name - participant_n (replace with your participant number, for example - participant_1)
*   Password - Same as above
*   Tables - transactions_participant_n, accounts_participant_n (replace with your participant number, for example - participant_1)

![cn1](images/connector-1.png)

![cn2](images/connector-2.png)

![cn3](images/connector-3.png)

![cn4](images/connector-4.png)

![cn5](images/connector-5.png)

![cn6](images/connector-6.png)

![cn7](images/connector-7.png)

![cn8](images/connector-8.png)

![cn9](images/connector-9.png)

---

###   `5.  Check the CDC data generated in the topic`

![tc1](images/topic-1.png)

![tc1](images/topic-2.png)

*   Insert records into tables -      

`INSERT INTO transactions_participant_n (account_id,amount,transaction_type) VALUES ('ACC1',5000,'DEPOSIT');`      

`INSERT INTO accounts_participant_n (account_id,first_name,last_name) VALUES ('ACC1','Suraj','Pillai');`                   

`(change the table names)`      

*   Check corresponding topics for records


