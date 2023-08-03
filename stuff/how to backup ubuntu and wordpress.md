To back up an Ubuntu server with WordPress installed, you need to create two separate backups: one for the server system files and configurations and another for the WordPress website's files and database.

Here's a step-by-step guide to perform both backups:

1. Backup Ubuntu Server System Files:
   Create a backup of the important system files and configurations on your Ubuntu server. This can be useful in case you need to restore the server to its current state.

   - Use `tar` to create a compressed archive of essential directories (e.g., `/etc`, `/home`, `/var`, etc.). Run the following command:

 ```bash
 sudo tar czvf server_backup.tar.gz /etc /home /var
```

   - Store the `server_backup.tar.gz` file in a safe location, preferably on an external storage device or cloud storage.

2. Backup WordPress Website Files and Database:
   Create a backup of your WordPress website's files and database. This ensures you can restore your website if anything goes wrong or if you need to migrate to a new server.

   - Backup WordPress Files:
     You can use `tar` or any other backup tool to create a compressed archive of your WordPress website directory. For example, to back up the entire WordPress directory located at `/var/www/html/`, use:

 ```bash
     sudo tar czvf wordpress_backup.tar.gz /var/www/html/
 ```

   - Backup WordPress Database:
     Use the `mysqldump` command to create a backup of your WordPress database. Replace `your_database_name`, `your_database_username`, and `your_database_password` with your actual database details:

 ```bash
     mysqldump -u your_database_username -p your_database_name > wordpress_database_backup.sql
 ```
  Example of this 
         
 ```bash
   mysqldump -u root -p wordpress_db_p2349080 > wordpress_database_backup.sql
 ```


  Enter the database password when prompted. This will create a file named `wordpress_database_backup.sql` containing the database structure and data.

   - Store both `wordpress_backup.tar.gz` and `wordpress_database_backup.sql` files in the same location as the server backup or in a separate backup directory.




