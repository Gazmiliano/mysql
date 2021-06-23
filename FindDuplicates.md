```sql
SELECT firstname, 
   lastname, 
   list.address 
FROM list
   INNER JOIN (SELECT address
               FROM   list
               GROUP  BY address
               HAVING COUNT(id) > 1) dup
           ON list.address = dup.address;
```           

```sql
SELECT id FROM table GROUP BY id having count(*) >= 2
```
