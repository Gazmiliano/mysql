### Enabling the mysql slow query log
Slow queries can affect database performance and overall server performance. The slow query log feature in MySQL enables you to log queries that exceed a predefined time limit. This greatly simplifies the task of finding inefficient or time-consuming queries.
To enable the slow query log in MySQL, follow these steps:
1.	Log in to your server using SSH.
2.	At the command line, type the following command:
>mysql -u root -p
3.	Type the MySQL root password.
4.	To enable the slow query log, type the following command at the mysql> prompt:
>SET GLOBAL slow_query_log = 'ON';
5.	There are additional options that you can set for the slow query log:
By default, when the slow query log is enabled, it logs any query that takes longer than 10 seconds to run. To change this interval, type the following command, replacing X with the time in seconds:
>SET GLOBAL long_query_time = X;

By default, the slow query log file is located at /var/lib/mysql/hostname-slow.log. To change the log path or filename, type the following command, replacing path with the path to the file, and filename with the name of the log filename:
>SET GLOBAL slow_query_log_file = '/path/filename';
6.	To verify that the slow query log is working correctly, log out of the mysql program, and then log back in. (This reloads the session variables for the mysql program.) Type the following command, replacing X with a value that is greater than the long_query_time setting:
>SELECT SLEEP(X);

The slow query log file should contain information about the query.
7.	Continue to monitor the slow query log file to see which queries take a long time to run.
8.	When you are done troubleshooting, disable the slow query log. To do this, run the mysql program again, and then type the following command:
>SET GLOBAL slow_query_log = 'OFF';

