Import more than 2 mb\
There is a couple of ways.
1) Split your SQL file into multiple 2MB chunks OR
2) update your php.ini file with the following (only works on dedicated/local servers - any server you have root on or ones that allow php.ini to be override)\
Find:
```
post_max_size = 8M
upload_max_filesize = 2M
max_execution_time = 30
max_input_time = 60
memory_limit = 8M
```

Change to: ( or any size you want but it will depend on your server resources )
```
post_max_size = 35M
upload_max_filesize = 35M
max_execution_time = 5000
max_input_time = 5000
memory_limit = 1000M
```
3) If you do have root run a command line
mysql -u username -p -D database_name < file

Examples
```
mysql -u username -p database_name < file.sql
mysqldump -u root -p --all-databases > alldb.sql
mysqldump -uuser -ppass --no-data --databases db1 db2 db3 > database_structure.sql
mysqldump -u root -p --no-data --databases --all-databases > database_structure.sql
```



