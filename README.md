# The fullstack excercise
![Coursera](https://img.shields.io/badge/Coursera-0747a6?style=flat&logo=coursera&logoColor=white)
![Meta](https://img.shields.io/badge/Meta-0668E1?style=flat&logo=meta&logoColor=white)
![Django](https://img.shields.io/badge/Django-092e20?style=flat&logo=django&logoColor=white)  

This is my solution to the fullstack excercise number 1 which requires connecting the Little Lemon back-end to MySQL.

## The excercise
Connect the Little Lemon back-end to MySQL

## Steps to Connect Little Lemon Back-end to MySQL

- [x] **Step 1:** Open your command line or terminal and log in to the MySQL shell:
  ```bash
  mysql -u root -p
  ```
  Press Enter and enter the password when prompted. If you need admin privileges, use:
  ```bash
  sudo mysql -u root -p
  ```

- [x] **Step 2:** Create a database named `reservations`:
  ```sql
  CREATE DATABASE reservations;
  ```

- [x] **Step 3:** Verify that the database has been created:
  ```sql
  SHOW DATABASES;
  ```

- [x] **Step 4:** Open VS Code, navigate to your Django project directory, and enable the pipenv virtual environment.

- [x] **Step 5:** Enter the MySQL shell again:
  ```bash
  mysql -u root -p
  ```

- [x] **Step 6:** Show databases to ensure `reservations` is present.

- [x] **Step 7:** Create a new user for the database:
  ```sql
  CREATE USER 'admindjango'@'localhost' IDENTIFIED BY 'employee@123!';
  ```

- [x] **Step 8:** Grant all permissions to the new user:
  ```sql
  GRANT ALL ON *.* TO 'admindjango'@'localhost';
  ```

- [x] **Step 9:** Flush all privileges:
  ```sql
  FLUSH PRIVILEGES;
  ```

- [x] **Step 10:** Exit the MySQL shell:
  ```sql
  EXIT;
  ```

- [x] **Step 11:** In your Django project, open `settings.py` and add `myapp` to `INSTALLED_APPS`.

- [x] **Step 12:** Update the `DATABASES` configuration in `settings.py` with the following values:
  ```python
  DATABASES = {
      'default': {
          'NAME': 'reservations',
          'USER': 'admindjango',
          'PASSWORD': 'employee@123!',
          'ENGINE': 'django.db.backends.mysql',
      }
  }
  ```

- [x] **Step 13:** Save the `settings.py` file.

- [x] **Step 14:** Run the command to make migrations in the terminal.

- [x] **Step 15:** Open `models.py` and review the `Booking` model.

- [x] **Step 16:** Run the migration commands to create the Booking table.

- [x] **Step 17:** Enter the MySQL shell again and check the Booking table:
  ```sql
  USE reservations;
  SHOW TABLES;
  DESCRIBE myapp_booking;
  ```

