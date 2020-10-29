# Bootcamp GoStack - Challenge 06

Practice repository using a Postgres database with docker and node.js. It creates income and outcome transactions on the database, returning your account balance.

It's also possible to import a csv file with a list of income/expenses to be stored as a book import on the database.

### Frontend

Frontend for this project is available at : https://github.com/SirKadogan/goFinances-frontend

### Technologies used

- Node.js
- Typescript
- TypeOrm
- Express
- Jest

### Instructions to run

You will need docker pre-installed for this project.

To create a Postgres image on your docker container:

`docker run --name postgres -d -p 5432:5432 -e POSTGRES_PASSWORD=docker postgres`

If port 5432 is occupied, you will need to find the next available port (5433 for example), and change the command to 5433:5432. Change the port on ormconfig.json file aswell.

- Create a connection to your Postgres Image on a DB Manager, such as DBeaver.
- Create a database called `gostack_desafio06` in your postgres connection in DBeaver.
- Create a database called `gostack_desafio06_tests` if you intend to run the tests

- Run `yarn` to install dependencies.
- Run `yarn run typeorm migration:run` to execute the migration and create the tables in your database.
- Run `yarn dev:server` to start the server.

### How to use

You will need to use Postman or Insomnia to be able to interact with the code.
A workspace file is provided at the root of this repository to be imported int Insomnia.

<b> List All transactions </b>
GET localhost:3333/transactions

<b> Create new transaction </b>
POST localhost:3333/transactions

Body must be a JSON

```
{
	"title": string,
	"value": number,
	"type": "income"| "outcome",
	"category": string
}
```

<b> Remove transaction </b>
DELETE localhost:3333/transactions/:id

<b> Book import transactions </b>
POST localhost:3333/import
</br>
<i>A csv example file is available at /src/** tests **</i>
