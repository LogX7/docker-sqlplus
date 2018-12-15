# Oracle SQL*Plus
docker image for oracle SQL*Plus with instant client

```bash
docker run --rm --net host -it logx7/sqlplus user/passwd@//host:port/SID
```

### Executing SQL Files From Your Host Machine:
you can do this by using bind mounts:

- create a folder to work in (create / edit / delete sql files)
    ```bash
    mkdir sql_files_folder
    ```
- run the container :
    ```bash
    docker run --rm -v /complete/path/to/sql_files_folder/:/opt/sql_files --net host -it logx7/sqlplus user/passwd@//host:port/SID
    ```

- to run an sql file that you added/edited it should exist in the `sql_files_folder`, you can do :
    ```sql
    @sql_files/file_name.sql
    ```