![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

Welcome Samuel Parker,

Postgres Database Project/Learning Example. 

LMS does not mention some of the following that needs to be done EVERY time you load your workspace (Thanks to Barrie for the scripts). 

Quirks

I created this script to refill the database every time this happened so I could focus on the new coding. Seems some of you might be running into similiar issues, so here's the steps to do it.\
1 - Create a file called create-fill-database.sh and fill it with the following information (correction: I added the two new pip3 commands to load required modules too) \
pip3 install sqlalchemy==1.4.46 \
pip3 install psycopg2 \
export PGHOSTADDR=127.0.0.1 \
psql -c "CREATE DATABASE chinook" \
psql -d chinook -f Chinook_PostgreSql.sql \
2 - Run the command - chmod 744 create-fill-database.sh \
3 - Run ./create-fill-database.sh \
4 - Run set_pg 


If you aren't sure if you have the database already, you can use the following commands inside the psql program to check:- \
\l - List the databases available, if chinook is there, you have it. \
\dt - Display the tables in your current database, this is useful if you aren't sure if content is in your chinook database. You'll need to have \c chinook first to get into the chinook database (assuming you have it) \
\c chinook - As mentioned above, this switches you to the chinook database 


Add the following code to remove the warning re deprecation:

from sqlalchemy.util import deprecations
deprecations.SILENCE_UBER_WARNING = True
