## Challenge 06

Practice repository using a Postgres database with docker and node.js. It creates income and outcome transactions on the database, returning your account balance.

It's also possible to import a csv file with a list of income/expenses to be stored as a book import on the database.

### Instructions to run

You will need docker pre-installed for this project.

To create a postgres image on your docker container:

`- docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres -p 5432:5432`

If port 5432 is occupied, you will need to find the next available port (5433 for example), and change the command to 5433:5432. Change the port on ormconfig.json file aswell.

- create a database called gostack_desafio06
- create a database called gostack_desafio06_tests if you intend to run the tests

- npm install or yarn
- yarn dev:server to run.

You will need to use postman or insomnia to be able to interact with the code.
