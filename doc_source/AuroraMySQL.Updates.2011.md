# Amazon Aurora MySQL Database Engine Updates 2018\-03\-13<a name="AuroraMySQL.Updates.2011"></a>

**Version:** 2\.01\.1

Amazon Aurora MySQL 2\.01\.1 is generally available\. Please note that Aurora MySQL 2\.x versions are compatible with MySQL 5\.7 and Aurora MySQL 1\.x versions are compatible with MySQL 5\.6\.

When creating a new Aurora MySQL DB cluster, you have the option of choosing compatibility with either MySQL 5\.7 or MySQL 5\.6\. When restoring a MySQL 5\.6\-compatible snapshot, you have the option of choosing compatibility with either MySQL 5\.7 or MySQL 5\.6\.

You can restore snapshots of Aurora MySQL 1\.14\*, 1\.15\*, 1\.16\*, and 1\.17\* into Aurora MySQL 2\.01\.1\.

We do not allow in\-place upgrade of Aurora MySQL 1\.x clusters into Aurora MySQL 2\.01\.1 or restore to Aurora MySQL 2\.01\.1 from an Amazon S3 backup\. We plan to remove these restrictions in a later Aurora MySQL 2\.x release\.

The performance schema is disabled for this release of Aurora MySQL 5\.7\. Upgrade to Aurora 2\.03 for performance schema support\.

## Comparison with Aurora MySQL 5\.6<a name="AuroraMySQL.Updates.2011.Compare56"></a>

The following Amazon Aurora MySQL features are supported in Aurora MySQL 5\.6, but these features are currently not supported in Aurora MySQL 5\.7\.
+ Asynchronous key prefetch \(AKP\)\. For more information, see [Working with Asynchronous Key Prefetch in Amazon Aurora](AuroraMySQL.BestPractices.md#Aurora.BestPractices.AKP)\.
+ Hash joins\. For more information, see [Working with Hash Joins in Aurora MySQL](AuroraMySQL.BestPractices.md#Aurora.BestPractices.HashJoin)\.
+ Native functions for synchronously invoking AWS Lambda functions\. For more information, see [Invoking a Lambda Function with an Aurora MySQL Native Function](AuroraMySQL.Integrating.Lambda.md#AuroraMySQL.Integrating.NativeLambda)\.
+ Scan batching\. For more information, see [Amazon Aurora MySQL Database Engine Updates 2017\-12\-11](AuroraMySQL.Updates.20171211.md)\.
+ Migrating data from MySQL using an Amazon S3 bucket\. For more information, see [Migrating Data from MySQL by Using an Amazon S3 Bucket](AuroraMySQL.Migrating.ExtMySQL.md#AuroraMySQL.Migrating.ExtMySQL.S3)\.

Currently, Aurora MySQL 2\.01\.1 does not support features added in Aurora MySQL version 1\.16 and later\. For information about Aurora MySQL version 1\.16, see [Amazon Aurora MySQL Database Engine Updates 2017\-12\-11](AuroraMySQL.Updates.20171211.md)\.

## MySQL 5\.7 compatibility<a name="AuroraMySQL.Updates.2011.Compatibility"></a>

Amazon Aurora MySQL 2\.01\.1 is wire\-compatible with MySQL 5\.7 and includes features such as JSON support, spatial indexes, and generated columns\. Amazon Aurora MySQL uses a native implementation of spatial indexing using z\-order curves to deliver >20x better write performance and >10x better read performance than MySQL 5\.7 for spatial datasets\.

Amazon Aurora MySQL 2\.01\.1 does not currently support the following MySQL 5\.7 features:
+ Global transaction identifiers \(GTIDs\)
+ Group replication plugin
+ Increased page size
+ InnoDB buffer pool loading at startup
+ InnoDB full\-text parser plugin
+ Multisource replication
+ Online buffer pool resizing
+ Password validation plugin
+ Query rewrite plugins
+ Replication filtering
+ The `CREATE TABLESPACE` SQL statement
+ X Protocol

## CLI differences between Aurora MySQL 2\.x and Aurora MySQL 1\.x<a name="AuroraMySQL.Updates.2011.CLI"></a>
+ The engine name for Aurora MySQL 2\.x is `aurora-mysql`; the engine name for Aurora MySQL 1\.x continues to be `aurora`\.
+ The engine version for Aurora MySQL 2\.x is `5.7.12`; the engine version for Aurora MySQL 1\.x continues to be `5.6.10ann`\.
+ The default parameter group for Aurora MySQL 2\.x is `default.aurora-mysql5.7`; the default parameter group for Aurora MySQL 1\.x continues to be `default.aurora5.6`\.
+ The DB cluster parameter group family name for Aurora MySQL 2\.x is `aurora-mysql5.7`; the DB cluster parameter group family name for Aurora MySQL 1\.x continues to be `aurora5.6`\.

Refer to the Aurora documentation for the full set of CLI commands and differences between Aurora MySQL 2\.x and Aurora MySQL 1\.x\.

## Improvements<a name="AuroraMySQL.Updates.2011.Improvements"></a>
+ Fixed an issue with snapshot restore where Aurora\-specific database privileges were created incorrectly when a MySQL 5\.6\-compatible snapshot was restored with MySQL 5\.7 compatibility\.
+ Added support for 1\.17 snapshot restores\.