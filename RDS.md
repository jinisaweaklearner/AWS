

# RDS overview
It allows you to create databases in the cloud that are managed by AWS 
- Postgres
- Oracle
- MySQL
- MariaDB
- Oracle
- Microsoft SQL Server
- Aurora (AWS Proprietary database)

# Advantage of using RDS
- Managed service
- OS patching level
- Continuous backups and restore to specific timestamp (Point in Time Restore)!
- Monitoring dashboards
- Read replicas for improved read performance
- Multi AZ setup for DR (Disaster Recovery)
- Maintenance windows for upgrades
- Scaling capability (vertical and horizontal)
- BUT you can’t SSH into your instances

# RDS Read Replicas for read scalability
- Up to 5 Read Replicas
- Within AZ, Cross AZ or Cross Region
- Replication is ASYNC, so reads are eventually consistent
- Replicas can be promoted to their own DB

# Aurora
- Postgres and MySQL are both supported as Aurora DB
- Aurora can have 15 replicas while MySQL has 5, and the replication process is faster
- Aurora costs more than RDS (20% more) – but is more efficient

# ElastiCache
- ElastiCache is to get managed Redis or Memcached
- Caches are in-memory databases with really high performance, low latency

# Different ports
Important ports:
- FTP: 21
- SSH: 22
- SFTP: 22 (same as SSH)
- HTTP: 80
- HTTPS: 443

vs RDS Databases ports:
- PostgreSQL: 5432
- MySQL: 3306
- Oracle RDS: 1521
- MSSQL Server: 1433
- MariaDB: 3306 (same as MySQL)
- Aurora: 5432 (if PostgreSQL compatible) or 3306 (if MySQL compatible)

## Redshift
- OLAP (online analytical processing)
- Scale to PB data
- Columnar storage of data


Amazon Redshift workload management (WLM) enables users to flexibly manage priorities within workloads so that short, fast-running queries won't get stuck in queues behind long-running queries.

- Automated Cross-Region Snapshot Copy for Amazon Redshift

You simply select the second region and the desired retention period; Redshift will take care of the rest: https://aws.amazon.com/blogs/aws/automated-cross-region-snapshot-copy-for-amazon-redshift/



## use DynamoDB for session data
https://aws.amazon.com/blogs/aws/scalable-session-handling-in-php-using-amazon-dynamodb/

## Types of Aurora Endpoints
- Cluster endpoint
  - perform write operations such as DDL statements
- Reader endpoint
  - provides load-balancing support for read-only connections to the DB cluster
- Custom endpoint
  - represents a set of DB instances that you choose
- Instance endpoint

## Redshift Encryption at rest
encrypts your data as it writes it in its data centers and decrypts it for you when you access it
