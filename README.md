# assignment20.2


sqoop import --connect jdbc:mysql://localhost/db1 \
--username 'root' -P --table 'company' --target-dir '/sqoopout' \
--hive-import \
--incremental append \
--check-column id \
-m 1;

insert into company values(4, 'maples','chennai');
insert into company values(5, 'kclink','hyderabad');
commit;

sqoop import --connect jdbc:mysql://localhost/db1 \
--username 'root' -P --table 'company' --target-dir '/sqoopout' \
--incremental append \
--check-column id \
--last-value 3 \
-m 1;

