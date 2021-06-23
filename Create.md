```sql
CREATE DATABASE dbname;

CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';

GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, INDEX, DROP, ALTER,
  CREATE TEMPORARY TABLES, LOCK TABLES ON dbname.* TO 'user'@'localhost';

GRANT FILE ON *.* TO 'user'@'localhost';

--- Change password
ALTER USER 'user'@'localhost' IDENTIFIED BY 'password';
SET PASSWORD FOR 'user-name-here'@'hostname' = PASSWORD('new-password');

--- Change user hostname
UPDATE mysql.user SET Host='127.0.0.1' WHERE Host='localhost' AND User='moderator';

--- If doesn't changed permissions
revoke all privileges on *.* from 'moderator'@'127.0.0.1';

FLUSH PRIVILEGES;
```
