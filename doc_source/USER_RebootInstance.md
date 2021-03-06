# Rebooting a DB Instance in a DB Cluster<a name="USER_RebootInstance"></a>

You might need to reboot your DB instance, usually for maintenance reasons\. For example, if you make certain modifications, or if you change the DB parameter group associated with the DB instance  or its DB cluster, you must reboot the instance for the changes to take effect\. 

Rebooting a DB instance restarts the database engine service\. Rebooting a DB instance results in a momentary outage, during which the DB instance status is set to *rebooting*\. 

You can't reboot your DB instance if it is not in the "Available" state\. Your database can be unavailable for several reasons, such as an in\-progress backup, a previously requested modification, or a maintenance\-window action\. 

**Important**  
When you reboot the primary instance of an Amazon Aurora DB cluster, RDS also automatically restarts all of the Aurora Replicas in that DB cluster\. When you reboot the primary instance of an Aurora DB cluster, no failover occurs\. When you reboot an Aurora Replica, no failover occurs\. To failover an Aurora DB cluster, call the AWS CLI command [https://docs.aws.amazon.com/cli/latest/reference/rds/failover-db-cluster.html](https://docs.aws.amazon.com/cli/latest/reference/rds/failover-db-cluster.html), or the API action [https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_FailoverDBCluster.html](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_FailoverDBCluster.html)\. 

## AWS Management Console<a name="USER_RebootInstance.Console"></a>

**To reboot a DB instance**

1. Sign in to the AWS Management Console and open the Amazon RDS console at [https://console\.aws\.amazon\.com/rds/](https://console.aws.amazon.com/rds/)\.

1. In the navigation pane, choose **Instances**, and then select the DB instance that you want to reboot\. 

1. Choose **Instance actions** and then choose **Reboot**\. 

   The **Reboot DB Instance** page appears\.

1. Choose **Reboot** to reboot your DB instance\. 

   Alternatively, choose **Cancel**\. 

## CLI<a name="USER_RebootInstance.CLI"></a>

To reboot a DB instance by using the AWS CLI, call the [https://docs.aws.amazon.com/cli/latest/reference/rds/reboot-db-instance.html](https://docs.aws.amazon.com/cli/latest/reference/rds/reboot-db-instance.html) command\. 

**Example Simple Reboot**  
For Linux, OS X, or Unix:  

```
1. aws rds reboot-db-instance \
2.     --db-instance-identifier mydbinstance
```
For Windows:  

```
1. aws rds reboot-db-instance ^
2.     --db-instance-identifier mydbinstance
```

## API<a name="USER_RebootInstance.API"></a>

To reboot a DB instance by using the Amazon RDS API, call the [https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_RebootDBInstance.html](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_RebootDBInstance.html) action\. 