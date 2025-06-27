
# Install dependencies:


pipenv install flask flask_sqlalchemy flask_migrate flask-jwt-extended psycopg2-binary pipenv shell✅ PostgreSQL DB setup

#Create your database in Postgres:

CREATE DATABASE late_show_db;

 # Set your DATABASE_URI in server/config.py

SQLALCHEMY_DATABASE_URI = "postgresql://<user>:<password>@localhost:5432/late_show_db"

 #Run DB setup

export FLASK_APP=server/app.py flask db init flask db migrate -m "initial migration" flask db upgrade python server/seed.py