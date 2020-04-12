*** Step one ***
Download pgAdmin: https://www.pgadmin.org/download/

Notes: Make sure to remamber the password you input during the dowloading process beacuse that's the password you are going to use to access the database.

*** Step Two ***
Assuming you've already created an `knexfile.js` make sure your `connection` looks like the code below

		connection: {
			host: process.env.POSTGRESS_DEV_HOST,
			port: process.env.POSTGRESS_DEV_PORT,
			user: process.env.POSTGRESS_DEV_USER,
			password: process.env.POSTGRESS_DEV_PASSWORD,
			database: process.env.POSTGRESS_DEV_DATABASE
		}

Create a `.env` file like below 

            POSTGRESS_DEV_HOST=localhost
            POSTGRESS_DEV_PORT=5432
            POSTGRESS_DEV_USER=username
            POSTGRESS_DEV_PASSWORD=password <-- same password as the one you use to sign in pgadmin
            POSTGRESS_DEV_DATABASE=databasename

*** Step Three *** 

Start server: `npm run server`

* if working locally 

Migrate data to base migration: `npx knex migrate:rollback`  

Migrate your tables: `npx knex migrate:up`