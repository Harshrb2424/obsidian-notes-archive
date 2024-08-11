Non-blocking PostgreSQL client for Node.js. Pure JavaScript and optional native libpq bindings.
https://node-postgres.com/

```js
import pg from "pg";

const client = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "TestDataBase",
  password: "1234",
  port: 1234,
});
//or
import { Client } from 'pg'
const client = new Client()
 
await client.connect()
 
const result = await client.query('SELECT NOW()')
console.log(result)
 
await client.end()

```