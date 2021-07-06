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
