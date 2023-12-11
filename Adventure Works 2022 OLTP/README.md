
# Adventure Works 2022 OLTP

This zip file contains the entire AdventureWorks 2022 OLTP database scripted out in T-SQL containing both the object schema and table data . 

This script can be used to re-create the AdventureWorks 2022 database on a SQL Server database. This script 
was scripted out using the  AdventureWorks2022.bak SQL backup file found here: 

https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms

Note that a couple of stored procedures were commented out as that code used full text catalogs which is not currently supported in Azure SQL. 

One use case for this script is to run it against the free Azure SQL database offer. There are restrictions with that 
that Azure SQL database, such as such restore from backup option. 

Another use case would be for running against other RDBMS such as MySQL and Postgres. That may take some modification to alter some T-SQL specific code. 

This script has been tested and build on against: 

 1. SQL Server 2022 
 2. Azure SQL Server (as of 2023-12-10)

## Instructions to run build in SQL Server Management Studio:

1. Change the database context name to match the deployment database name for deployment. 
2. Click **Query** -> **Specify Values for Template Parameters**
3. In the Values column for the **pathtorootfolder** parameter, type in the path to the root folder for the local repo without trailing backslash (e.g. C:\Repo\Dw2022). Click **OK**.
4. Click **Query** -> **SQLCMD** mode.
5. Execute the build script.
