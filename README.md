install 
```sh
# npm
npm i @adonisjs/lucid
```

Support for multiple SQL database. PostgreSQL, MySQL, MSSQL, MariaDB and SQLite.

The configuration for all the database drivers is stored inside the `config/database.ts` file, then config in `.env` : 
```sh
PORT=
HOST=0.0.0.0
NODE_ENV=development
SESSION_DRIVER=cookie
CACHE_VIEWS=false
DB_CONNECTION=pg
PG_HOST=localhost
PG_PORT=
PG_USER=
PG_PASSWORD=
PG_DB_NAME=

```
Usage in the following example, we select all the posts from the `posts` table.
```sh
import Database from '@ioc:Adonis/Lucid/Database'
import Route from '@ioc:Adonis/Core/Route'

Route.get('posts', async () => {
  return Database.from('posts').select('*')
})

```
Driver Config
```sh
npm i sqlite3
```
```sh
sqlite: {
  client: 'sqlite',
  connection: {
    filename: Application.tmpPath('db.sqlite3'),
  },
  migrations: {
    naturalSort: true,
  },
  useNullAsDefault: true,
  healthCheck: false,
  debug: false,
}
```

```sh
nnpm i mysql
```
```sh
mysql: {
  client: 'mysql',
  connection: {
    host: Env.get('MYSQL_HOST'),
    port: Env.get('MYSQL_PORT'),
    user: Env.get('MYSQL_USER'),
    password: Env.get('MYSQL_PASSWORD', ''),
    database: Env.get('MYSQL_DB_NAME'),
  },
  migrations: {
    naturalSort: true,
  },
  healthCheck: false,
  debug: false,
}
```
```sh
npm i pg
```
```sh
pg: {
  client: 'pg',
  connection: {
    host: Env.get('PG_HOST'),
    port: Env.get('PG_PORT'),
    user: Env.get('PG_USER'),
    password: Env.get('PG_PASSWORD', ''),
    database: Env.get('PG_DB_NAME'),
  },
  migrations: {
    naturalSort: true,
  },
  healthCheck: false,
  debug: false,
}
```
```sh
npm i oracledb
```
```sh
oracle: {
  client: 'oracledb',
  connection: {
    host: Env.get('ORACLE_HOST'),
    port: Env.get('ORACLE_PORT'),
    user: Env.get('ORACLE_USER'),
    password: Env.get('ORACLE_PASSWORD', ''),
    database: Env.get('ORACLE_DB_NAME'),
  },
  migrations: {
    naturalSort: true,
  },
  healthCheck: false,
  debug: false,
}
```
```sh
npm i tedious
```
```sh
mssql: {
  client: 'mssql',
  connection: {
    user: Env.get('MSSQL_USER'),
    port: Env.get('MSSQL_PORT'),
    server: Env.get('MSSQL_SERVER'),
    password: Env.get('MSSQL_PASSWORD', ''),
    database: Env.get('MSSQL_DB_NAME'),
  },
  migrations: {
    naturalSort: true,
  },
  healthCheck: false,
  debug: false,
}
```
