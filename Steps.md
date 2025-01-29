Create a mysql db `sudo apt install mysql-server`
Create table within the MySql DB `sudo mysql -u root -e "CREATE DATABASE todo_db";`
Create a user for the mysql db `sudo mysql -u root -e "CREATE USER 'paige'@'localhost' IDENTIFIED BY 'password'";`
Grand necessary privileges required for user to make edits to the entire database `sudo myql -u root -e "GRANT ALL PRIVILEGES ON *.* TO 'paige'@'localhost' WITH GRANT OPTION";`
Clone down the git repo 
