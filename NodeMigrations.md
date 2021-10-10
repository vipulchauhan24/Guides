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
- Run `sequelize db:migration create` to create migration file.

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