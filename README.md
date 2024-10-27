# Final_Project-With-Sentiment-Analaysis-and-DataBase



## Installation and Setup

To get started , follow these steps to set up your environment and install the necessary dependencies.

### Prerequisites
- Python (version 3.7 or later)
- pip (Python package manager)
- Access to a command-line interface
- Setup Database
  
1. Set up the MySQ database:

    Open a MySQL Workbench client and run the following commands to create the database and table:

    ```sql
            CREATE DATABASE IF NOT EXISTS `login` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
            USE `login`;
            
            CREATE TABLE IF NOT EXISTS `accounts` (
            	`id` int(11) NOT NULL AUTO_INCREMENT,
            	`username` varchar(50) NOT NULL,
            	`password` varchar(255) NOT NULL,
            	`email` varchar(100) NOT NULL,
            	PRIMARY KEY (`id`)
            );
            
            ALTER TABLE accounts ADD preferences TEXT;
            
            CREATE TABLE articles (
                `id` INT AUTO_INCREMENT PRIMARY KEY,
                `title` VARCHAR(255),
                `link` TEXT,
                `full_text` TEXT,
                `summary` TEXT,
                `question` TEXT,
                `image_url` TEXT,
                `category` VARCHAR(255)
            );
            
            ALTER TABLE articles ADD COLUMN sentiment VARCHAR(10);
            ALTER TABLE articles ADD COLUMN timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP;

    ```

2. Configure the database connection in `app.py`:

   Open `app.py` and ensure the MySQL configurations are set correctly:

    ```python
    app.config['MYSQL_HOST'] = 'localhost'
    app.config['MYSQL_USER'] = 'root'
    app.config['MYSQL_PASSWORD'] = 'your_password'
    app.config['MYSQL_DB'] = 'login'
    ```


### Step 1: Clone the Repository
First, clone the repository to your local machine:
```bash
git clone https://github.com/shubhamade79/Final_Project-With-Sentiment-Analaysis-and-DataBase.git
cd Final_Project-With-Sentiment-Analaysis-and-DataBase
```

### Step 2: Install Dependencies
Install all the required libraries using pip:
Backend
```bash
pip install Flask transformers requests beautifulsoup4 flask-mysqldb textblob apscheduler mysqlclient
```
Frontend
```
pip install Flask flask-mysqldb mysqlclient

```
### Step 3: Run App.py File
```bash
python app.py  
```
And
```bash
python show_articles.py
```
### Step 4: Click the link On Terminal Then Open The Website
```bash
(http://127.0.0.1:5000)
And
(http://127.0.0.1:5001)
```
