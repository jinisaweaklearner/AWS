

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