# Steps to use Sequalize to automatically create database and table in node js.

## step 1
- Run command `npm install --save sequelize` & `npm install --save sequelize-cli`

## Step 2
### Run one of the following:

- `npm install --save pg pg-hstore`
- `npm install --save mysql2` // For both mysql and mariadb dialects
- `npm install --save sqlite3`
- `npm install --save tedious` // MSSQL

## Step 3
- Run following command `sequelize init`. if running in windows first run the following command - `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` to bypass powershell prompts.

## Step 4
- Delete models folder.

## Step 3 
## Below Code to setup database

var sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: 'mysql'|'mariadb'|'sqlite'|'postgres'|'mssql',

  pool: {
    max: 5,
    min: 0,
    idle: 10000
  },

  // SQLite only
  storage: 'path/to/database.sqlite'
});

// Or you can simply use a connection uri
var sequelize = new Sequelize('postgres://user:pass@example.com:5432/dbname');`

## Step 4
### Creating models
var User = sequelize.define('user', {
  firstName: {
    type: Sequelize.STRING,
    field: 'first_name' // Will result in an attribute that is firstName when user facing but first_name in the database
  },
  lastName: {
    type: Sequelize.STRING
  }
}, {
  freezeTableName: true // Model tableName will be the same as the model name
});

User.sync({force: true}).then(function () {
  // Table created
  return User.create({
    firstName: 'John',
    lastName: 'Hancock'
  });
});