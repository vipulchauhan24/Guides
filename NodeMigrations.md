# Steps to setup migrations of tables in node and connecting to database.

## Step 1
- `npm install --save sequelize`
- `npm install --save sequelize-cli`
- `npm install mysql2`

## Step 2
- `npx sequelize init`

## Step 3
- Configure the config.json file.

## Step 4
- Create a connection.js file using below code -

const Sequelize = require('sequelize');

const sequelize = new Sequelize("database_name", "username", "password",{
    host: "localhost",
    dialect : "mysql"
} );

module.exports = sequelize;
global.sequelize= sequelize;

## Step 5
- Create a model. for example - users.js
const Sequelize = require('sequelize');
const sequelize = require('../database/connection');

module.exports = sequelize.define('user',{
    id : { 
        type : Sequelize.INTEGER, 
        allowNull: false, 
        unique: true, 
        primaryKey: true,
        autoIncrement: true
    },
    email: {
        type: Sequelize.STRING(50),
        allowNull: false,
        unique: true
    },
    password : {
        type: Sequelize.STRING(500)
    }
})

## Step 6
- Run `sequelize db:migration create --name migrations` to create migration file.

## Step 7

- use bellow code in migrations file 
queryInterface.createTable('users', {
      id : { 
        type : Sequelize.INTEGER, 
        allowNull: false, 
        unique: true, 
        primaryKey: true,
        autoIncrement: true
      },
      email: {
          type: Sequelize.STRING(50),
          allowNull: false,
          unique: true
      },
      password : {
          type: Sequelize.STRING(500)
      },
      createdAt: Sequelize.DATE,
      updatedAt: Sequelize.DATE
})

## Step 8 
- Run `sequelize db:migrate` to migrate.


# Mysql Migration(ORM) using sequelize

## create config file using following code as an example

$ `module.exports = {
    HOST: "localhost",
    USER: "root",
    PASSWORD: "",
    DB: "e_comm",
    dialect: "mysql",
    pool: {
      max: 5,
      min: 0,
      acquire: 30000,
      idle: 10000
    }
};`

## create models js file with following code as an example

$ const dbConfig = require("../config/db.config.js");

const Sequelize = require("sequelize");
const sequelize = new Sequelize(dbConfig.DB, dbConfig.USER, dbConfig.PASSWORD, {
  host: dbConfig.HOST,
  dialect: dbConfig.dialect,
  operatorsAliases: false,

  pool: {
    max: dbConfig.pool.max,
    min: dbConfig.pool.min,
    acquire: dbConfig.pool.acquire,
    idle: dbConfig.pool.idle
  }
});

const db = {};

db.Sequelize = Sequelize;
db.sequelize = sequelize;

db.tutorials = require("./tutorial.model.js")(sequelize, Sequelize);

module.exports = db;

## create table model file using following code as an example

$ `module.exports = (sequelize, Sequelize) => {
  const Tutorial = sequelize.define("tutorial", {
    title: {
      type: Sequelize.STRING
    },
    description: {
      type: Sequelize.STRING
    },
    published: {
      type: Sequelize.BOOLEAN
    }
  });

  return Tutorial;
};`

## methods to be used in controller

After initializing Sequelize, we don’t need to write CRUD functions, Sequelize supports all of them:

- create a new Tutorial: create(object)
- find a Tutorial by id: findByPk(id)
- get all Tutorials: findAll()
- update a Tutorial by id: update(data, where: { id: id })
- remove a Tutorial: destroy(where: { id: id })
- remove all Tutorials: destroy(where: {})
- find all Tutorials by title: findAll({ where: { title: ... } })

These functions will be used in our Controller.