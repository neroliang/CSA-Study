====================

AWS Redshift

Amazon Redshift is a fully managed, fast and powerful, petabyte scale data warehouse service
Redshift automatically helps
set up, operate, and scale a data warehouse, from provisioning the infrastructure capacity
patches and backs up the data warehouse, storing the backups for a user-defined retention period
monitors the nodes and drives to help recovery from failures
significantly lowers the cost of a data warehouse, but also makes it easy to analyze large amounts of data very quickly
provide fast querying capabilities over structured data using familiar SQL-based clients and business intelligence (BI) tools using standard ODBC and JDBC connections.
uses replication and continuous backups to enhance availability and improve data durability and can automatically recover from node and component failures.
scale up or down with a few clicks in the AWS Management Console or with a single API call
distribute & parallelize queries across multiple physical resources
supports VPC, SSL, AES-256 encryption and Hardware Security Modules (HSMs) to protect the data in transit and at rest.
Redshift only supports Single-AZ deployments and the nodes are available within the same AZ, if the AZ supports Redshift clusters
Redshift provides monitoring using CloudWatch and metrics for compute utilization, storage utilization, and read/write traffic to the cluster are available with the ability to add user-defined custom metrics
Redshift provides Audit logging and AWS CloudTrail integration
Redshift can be easily enabled to a second region for disaster recovery.

# Redshift Architecture

# Redshift Performance

Massively Parallel Processing (MPP)
automatically distributes data and query load across all nodes.
makes it easy to add nodes to the data warehouse and enables fast query performance as the data warehouse grows.

# Columnar Data Storage
organizes the data by column, as column-based systems are ideal for data warehousing and analytics, where queries often involve aggregates performed over large data sets
columnar data is stored sequentially on the storage media, and require far fewer I/Os, greatly improving query performance

# Advance Compression
Columnar data stores can be compressed much more than row-based data stores because similar data is stored sequentially on disk.
employs multiple compression techniques and can often achieve significant compression relative to traditional relational data stores.
doesn’t require indexes or materialized views and so uses less space than traditional relational database systems.
automatically samples the data and selects the most appropriate compression scheme, when the data is loaded into an empty table
Redshift Single vs Multi-Node Cluster

Single Node
single node configuration enables getting started quickly and cost-effectively & scale up to a multi-node configuration as the needs grow

Multi-Node
Multi-node configuration requires a leader node that manages client connections and receives queries, and two or more compute nodes that store data and perform queries and computations.

# Leader node
provisioned automatically and not charged for
receives queries from client applications, parses the queries and develops execution plans, which are an ordered set of steps to process these queries.
coordinates the parallel execution of these plans with the compute nodes, aggregates the intermediate results from these nodes and finally returns the results back to the client applications.

Compute node can contain from 1-128 compute nodes, depending on the node type
executes the steps specified in the execution plans and transmit data among themselves to serve these queries.
intermediate results are sent back to the leader node for aggregation before being sent back to the client applications.
supports Dense Storage or Dense Compute nodes (DC) instance type

Dense Storage (DS) allow creation of very large data warehouses using hard disk drives (HDDs) for a very low price point
Dense Compute (DC) allow creation of very high performance data warehouses using fast CPUs, large amounts of RAM and solid-state disks (SSDs)
direct access to compute nodes is not allowed

# Redshift Availability & Durability

Redshift replicates the data within the data warehouse cluster and continuously backs up the data to S3 (11 9’s durability)
Redshift mirrors each drive’s data to other nodes within the cluster.
Redshift will automatically detect and replace a failed drive or node
If a drive fails, Redshift
cluster will remain available in the event of a drive failure
the queries will continue with a slight latency increase while Redshift rebuilds the drive from replica of the data on that drive which is stored on other drives within that node
single node clusters do not support data replication and the cluster needs to be restored from snapshot on S3

In case of node failure(s), Redshift
automatically provisions new node(s) and begins restoring data from other drives within the cluster or from S3
prioritizes restoring the most frequently queried data so the most frequently executed queries will become performant quickly
cluster will be unavailable for queries and updates until a replacement node is provisioned and added to the cluster
In case of Redshift cluster AZ goes down, Redshift
cluster is unavailable until power and network access to the AZ are restored
cluster’s data is preserved and can be used once AZ becomes available
cluster can be restored from any existing snapshots to a new AZ within the same region
Redshift Backup & Restore
Redshift replicates all the data within the data warehouse cluster when it is loaded and also continuously backs up the data to S3
Redshift always attempts to maintain at least three copies of the data
Redshift enables automated backups of the data warehouse cluster with a 1-day retention period, by default, which can be extended to max 35 days
Automated backups can be turned off by setting the retention period as 0
Redshift can also asynchronously replicate the snapshots to S3 in another region for disaster recovery
Redshift Scalability
Redshift allows scaling of the cluster either by
increasing the node instance type (Vertical scaling)
increasing the number of nodes (Horizontal scaling)
Redshift scaling changes are usually applied during the maintenance window or can be applied immediately
Redshift scaling process
existing cluster remains available for read operations only while a new data warehouse cluster gets created during scaling operations
data from the compute nodes in the existing data warehouse cluster is moved in parallel to the compute nodes in the new cluster
when the new data warehouse cluster is ready, the existing cluster will be temporarily unavailable while the canonical name record of the existing cluster is flipped to point to the new data warehouse cluster

# Redshift vs EMR vs RDS

RDS is ideal for
structured data and running traditional relational databases while offloading database administration
for online-transaction processing (OLTP) and for reporting and analysis

Redshift is ideal for
large volumes of structured data that needs to be persisted and queried using standard SQL and existing BI tools
analytic and reporting workloads against very large data sets by harnessing the scale and resources of multiple nodes and using a variety of optimizations to provide improvements over RDS
preventing reporting and analytic processing from interfering with the performance of the OLTP workload

EMR is ideal for
processing and transforming unstructured or semi-structured data to bring in to Amazon Redshift and
for data sets that are relatively transitory, not stored for long-term use.
