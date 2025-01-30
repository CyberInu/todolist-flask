Have Terraform create the resources <br> `terraform apply`<br>
Have Terraform create and output json file to capture the IP address of ec2 Instance <br>`terraform output -json > terraform-output.json`<br>
Run Ansible Flask role which does the following:<br>
Create a mysql db <br> `sudo apt install mysql-server`<br>
Create table within the MySql DB <br>`sudo mysql -u root -e "CREATE DATABASE todo_db";`<br>
Create a user for the mysql db <br>`sudo mysql -u root -e "CREATE USER 'paige'@'localhost' IDENTIFIED BY 'password'";`<br>
Grand necessary privileges required for user to make edits to the entire database <br>`sudo myql -u root -e "GRANT ALL PRIVILEGES ON *.* TO 'paige'@'localhost' WITH GRANT OPTION";`<br>
Clone down the git repo <br>`git clone https://github.com/CyberInu/todolist-flask.git`<br>
Change directory into the todo folder<br> `cd todolist-flask`<br>
Create a virtual environment <br>`python3 -m venv menv`<br>
Start the virtual environment <br>`source ./menv/bin/activate`<br>
Install the requirements.txt <br>`pip3 install -r requirements.txt`<br>
Run gunicorn <br>`gunicorn -w --bind 0.0.0.0:8000 wsgi:app`<br>
Check to see if page loaded correctly confirm database works<br>

<br>Architecture Diagram<br>

+---------------------+  
|  Security Group     |  
| +----------------+  |  
| |  EC2 Instance   |  |  
| | +------------+ |  |  
| | |  Flask App |<----+  
| | |  (Port 80)  |  |  
| | +------------+ |  |  
| | +------------+ |  |  
| | | MySQL DB   |  |  
| | | (Port 3306)|  |  
| | +------------+ |  |  
| +----------------+  |  
+---------------------+  

