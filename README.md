# node-postgres

###Step 1:
Go to http://postgresapp.com/ download and start the server

Download this https://eggerapps.at/postico/.

Postico is essentially Robomongo for Postgres

Open up Postico enter a nickname and password (dont forget the password)

Click on 'SQL Query'

Enter ```CREATE DATABASE [database name]```

Click Execute Statement

Verify by clicking your username next to the elephant in the status bar at the top

###Step 2: 
Create a new express app

```npm install```

Install node-postgres
```npm install --save pg```

```var pg = require('pg');```

```var connectionString = process.env.DATABASE_URL || 'postgres://localhost:5432/[YOUR-DATABASE-NAME]';```

