# MySQL lab

In this example:

* MySQL cluster is deployed using Oracle MySQL Operator

Tasks:

0. Adjust sandbox name `3nk45yqd6e` as necessary for your sandbox
1. Provision MySQL root password secret either manually,
   with `kubectl create secret generic -n sandbox-name-goes-here mysql-secrets --from-literal=rootPassword=$(cat /dev/urandom | base64 | head -c 30)`
   or using
   https://git.k-space.ee/k-space/generated-secret-operator
2. Using kubectl forward the router instance port to your local laptop and attempt
   to connect using MySQL command line utilities
3. Attempt to load `employees.sql` from https://github.com/datacharmer/test_db
   using the forwarded port
4. Verify using phpMyAdmin that the content got loaded into MySQL cluster
5. Deploy your favourite application that uses MySQL

Questions:

* Why is non-redundant storage class used here?
* What are the benefits and drawbacks using application level replication opposed to block level replication?
* What could be other options for MySQL cluster pod anti affinity topology key?
* Where/how can you figure out current cluster status?
* Which pod is the current primary?
* What are the options for monitoring the MySQL cluster?
* What are the benefits and drawbacks of managing MySQL databases yourself
  versus using SaaS offering such as AWS RDS?
* How does https://crossplane.io/ fit in the picture?
* How large instances to consider? When is sharding applicable?
