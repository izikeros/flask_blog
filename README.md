# Simple Flask App
This is a simple blog app based on serie of tutorials: [Python Flask from Scratch](https://www.youtube.com/watch?v=zRwy8gtgJ1A&list=PLillGF-RfqbbbPz6GSEM9hLQObuQjNoj_)
* user registration
* login and access control
* dashbord with list of articles with possibility to `edit` or `delete` each article



# install mysql and tools:
NOTE: mariadb was used as replacement for mysql

For Arch linux:
```bash
$ pacman -S mariadb libmariadbclient
```

```bash
$ pip install flask-mysqldb

# form validation, ...
$ pip install Flask-WTF

# password hashing
$ pip install passlib
```

# Handy mysql commands
Enter mysql:
```bash
$ mysql -u root -p
```

Show existing databases:
```sql
> SHOW DATABASES
```

Create new database:
```sql
> CREATE DATABASE myflaskapp;
```

Use our database:
```sql
> USE myflaskapp
```

Create table with articles:
```sql
> CREATE TABLE articles (id INT(11) AUTO_INCREMENT PRIMARY KEY, title VARCHAR(255), author VARCHAR(100), body TEXT, create_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
```

List all tables to check if table was created:
```sql
> SHOW TABLES;
```

List all articles:
```sql
> SELECT * FROM articles
```

Create table with users
```sql
> CREATE TABLE users(id INT(11) AUTO_INCREMENT PRIMARY KEY, name VARCHAR(100), email VARCHAR(100), username VARCHAR(30), password VARCHAR(100), register_date TIMESTAMP CURRENT_TIMESTAMP);
```

Get info on users table
```sql
> DESCRIBE users
```

# Ideas for further development of the app:
* Clean up the app.py into separate modules
* Customize it with your own stylesheets and javascript
* Add another layer of access control to delete_article (The users can create a fake html form to send post requests to /delete_article and delete other peoples articles.)
* Prevent users from registering the same username as other users.
* If a new user is login, then that should see only their artices not all the articles
* Send email confirmation to activate account, be able to edit both the username and password.
* Only let logged user delete or edit their own posts or only let admin user do it. Also, instead of logging in with username use email as username and only allow unique emails to be added to the database, even let only unique usernames be stored in DB.﻿
* you can use 'itsdangerous' python library for confirmation token and 'Flask-Mail' library to send confirmation mail to the newly registered user. # Follow the following links for brief documentation :
    - https://pythonhosted.org/itsdangerous/
    - https://pythonhosted.org/Flask-Mail/﻿
* Replace bootstrap with Semantic UI