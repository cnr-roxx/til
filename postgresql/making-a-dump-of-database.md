# Making A Dump Of Database

To backup whole Postgresql database just type in console:

```bash
$ sudo -u postgres pg_dump name_of_database > /tmp/dump_file_name.sql
```

"postgres" is name of user with privileges to "name_of_database" DB and it's default user running postgresql daemon on CentOS7.
