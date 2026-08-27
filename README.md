# Cyber Security Base Project

I use my previous Link Manager web application as the baseline template for this course project. I implemented security flaws from the following categories based on the [OWASP Top 10:2021](https://owasp.org/Top10/2021/) list, while their fixes are commented out in the code.

## Implemented flaws

1. Broken Access Control
2. Cryptographic Failures
3. Injection
4. Identification and Authentication Failures
5. Security Logging and Monitoring Failures

## Application description

Link Manager is a web application for saving, organising and searching useful links.

The application contains the following features:

* Users can create an account, log in and log out
* Users can add, edit and delete their own links
* Users can view links added by all users to the application
* Users can search for links by title, URL, notes or category
* Users can assign one optional primary category to a link
* Users can add comments containing additional information to links
* Users have profile pages and can view other users' profile pages with user activity statistics and links added by the user

## Guide for installing and running the application

Run the following commands depending on your operating system. The application requires Python 3 and SQLite 3. Flask is installed as a Python dependency in the virtual environment. Setting a local Flask secret key is also needed. 

### Linux

Install the required system packages if not yet installed:

```
sudo apt update
sudo apt install python3 python3-venv python3-pip sqlite3 git
```

Run the following commands in the terminal: 

```
git clone https://github.com/saanaol/csb-project
cd csb-project
python3 -m venv venv
source venv/bin/activate
pip install flask
sqlite3 database.db < schema.sql
sqlite3 database.db < init.sql
export SECRET_KEY=$(python3 -c 'import secrets; print(secrets.token_hex(32))')
flask run
```

Then you can open the application in your browser.

### macOS

Install the required system packages if not yet installed:

```
brew install python sqlite git
```

Run the following commands in the terminal: 

```
git clone https://github.com/saanaol/csb-project.git
cd csb-project
python3 -m venv venv
source venv/bin/activate
pip install flask
sqlite3 database.db < schema.sql
sqlite3 database.db < init.sql
export SECRET_KEY=$(python3 -c 'import secrets; print(secrets.token_hex(32))')
flask run
```

Then you can open the application in your browser.

### Windows (PowerShell)

Install Python 3, SQLite 3, and Git if they are not yet installed.

Run the following commands in PowerShell:

```
git clone https://github.com/saanaol/csb-project.git
cd csb-project
python -m venv venv
.\venv\Scripts\Activate.ps1
python -m pip install flask
sqlite3 database.db ".read schema.sql"
sqlite3 database.db ".read init.sql"
$env:SECRET_KEY = python -c "import secrets; print(secrets.token_hex(32))"
python -m flask run
```

Then you can open the application in your browser.
