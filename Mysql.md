## Import from dump .sql file
- `source <path_to_file>/file.sql`

## dump database to sql file
- `mysqldump -u root -p <database_name> > <path>/<file_name>.sql`

## remove sudo 
- `CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';`

- `GRANT ALL PRIVILEGES ON *.* TO 'newuser'@'localhost';`
