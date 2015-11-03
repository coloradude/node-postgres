# node-postgres
Most of this was taken/modified from http://mherman.org/blog/2015/02/12/postgresql-and-nodejs/

Follow along with him if this sucks 

![](https://imgs.xkcd.com/comics/exploits_of_a_mom.png)

![](http://farm6.static.flickr.com/5130/5310748684_f0fe7311dd.jpg)
###Step 1: Set up the database
Go to http://postgresapp.com/ download and start the server

Download this https://eggerapps.at/postico/.

Postico is essentially Robomongo for Postgres

Open up Postico enter a nickname and password (dont forget the password)

Click on 'SQL Query'

Enter ```CREATE DATABASE [database name]```

Click Execute Statement

Verify by clicking your username next to the elephant in the status bar at the top

###Step 2: Start your app
Create a new express app

```npm install```

Install node-postgres
```npm install --save pg```

Put this in your index.js file

```javascript
var pg = require('pg');
var connectionString = process.env.DATABASE_URL || 'postgres://localhost:5432/[YOUR-DATABASE-NAME]';
```

###Step 3: Build Tables (collections)

```javascript
pg.connect();
var query = client.query('CREATE TABLE items(id SERIAL PRIMARY KEY, text VARCHAR(40) not null, complete BOOLEAN)');
query.on('end', function() {
  done();
});
```

Save this as database.js in a new folder called "models".

Here we interact with the database and then establish communication with it via the connect() method. We then set run a SQL query via the query() method. Communication is closed via the done() method. Be sure to check out the documentation for more info


###More resources

http://stackoverflow.com/questions/8484404/what-is-the-proper-way-to-use-the-node-js-postgresql-module
