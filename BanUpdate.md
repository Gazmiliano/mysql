Update ban

```sql
DELIMITER
CREATE TRIGGER table_name_before_del_tr
BEFORE DELETE
   ON table_name FOR EACH ROW
   BEGIN
         SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'DELETE canceled'; 
END;
DELIMITER ;
```
