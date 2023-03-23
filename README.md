<h1> MySQL Server Upgrade Demo Project </h1>

<p> This demo project aims to provide a step-by-step guide for upgrading a MySQL Server from version 5.7 to 8.0.15. The project involves various processes, including configuring Master-Slave GTID Replication, Xrtrabackup, and many more used in the MySQL environment. This project will help beginners learn MySQL by providing practical demonstrations. </p>

<h2>Steps Involved </h2>

<h3> Step 1: Launching two servers for Master and Slave & Installing MYSQL 5.7 version!! </h3>

<h3>Step 2: Installing Dependencies on Both Servers</h3>

	-Installing Percona XtraBackup 2.4
	-Installing Percona Toolkit
	-Screen installation
	
<h3>Step 3: Importing data into MASTER mysql 5.7 DATABASE</h3>

	-Importing data into MySQL master server
	-Adding variables in my.cnf on master slave
	-Creating tables, inserting data, and procedure on only master node
	-Using screen to call procedure

<h3>Step 4: Creating Multiple MySQL Users Locally and Remotely on master node</h3>

<h3>Step 5: Restoring Data to MySQL Slave Server using XtraBackup Tool</h3>

<h3>Step 6: Configuring MySQL 5.7 Master-Slave GTID Replication</h3>

<h3>Step 7: Upgrading Slave Node 5.7 to 5.8.20</h3>

Before upgrading the slave node, the following steps need to be taken:

	-Verify the data count on both the master and slave nodes to ensure that they match.
	-Check the "my.cnf" configuration file and ensure that it is compatible with the latest version.
	-Collect all production queries by setting the slow query log value to -0.
	-Use the pt-query-digest tool to merge duplicate queries and obtain a unique set of slow queries.
	-Optional: Use the pt-fingerprint tool to obtain query structure information.
	-Back up user grants from both the master and slave databases using the pt-show-grants tool, to enable easy restoration of users in case of any issues or crashes.
	-Back up stored procedures, event schedulers, databases, and triggers.
	-Take a backup using xtrabackup to facilitate easy restoration and slave configuration.
	-Use the pt-upgrade tool to check the upgrade process. This tool simplifies and facilitates the upgrade process, making it easy to understand and follow.

<h3> Step 8: Configuring MySQL 5.7 Master - 8.0.15 Slave GTID Replication</h3>
	
<h3> Step 9: Upgrade the MySQL version of the master server from 5.7 to 8.0.15</h3>

	-Before upgrading, make sure to drop the stored procedures or restore them onto the slave server. Verify that they are running without issues on the slave server before proceeding with the upgrade.

<h3>Step 10: Switching the role</h3>

To switch the role, we need to make the "MySQL slave server" the new "MySQL master server":

	-This involves moving the data backup from the slave server (new master) to the master server (new slave).
	-We will need to use xtrabackup again for this process.
	-Once the data is moved to the old master server (new slave), the old master server data should be removed.
	
<h3> Step 11: Configuring new MySQL Master - new MySQL Slave NORMAL Replication</h3>



Congratulations! You have successfully completed this demo project. These steps should help you understand MySQL and its various processes better. 

<h3> Documentation</h3>

For more detailed information about the steps involved in this project, please refer to the attached documentation.

Thank you for taking the time to read this README :) 
