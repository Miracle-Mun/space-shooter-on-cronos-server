# Crosmo Shooter ![License](https://img.shields.io/badge/license-MIT-blue) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-green.svg)

## Built with

- [Phaser3](https://github.com/photonstorm/phaser) - Game engine
- [Colyseus](https://github.com/colyseus/colyseus) - WebSocket-based server framework
- [React/Redux](https://github.com/facebook/react) - Front-end framework
- [TypeScript](https://github.com/microsoft/TypeScript) and [ES6](https://github.com/eslint/eslint) - for both client and server sides

## Prerequisites

- [Node.js](https://nodejs.org/) 
- [NPM](https://www.npmjs.com/) 
- [MonogDB](https://www.mongodb.com/)
- [PM2](https://pm2.keymetrics.io/)

## Configuration the System and Package Manager
>### Install Node and NPM on Ubuntu System
See this blog [How To Install Node.js and NPM on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04)
>### Install MongoDB and Set Configuration on Ubuntu System
- To install MongoDB service, see this [How To Install MongoDB on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-20-04)
- To set user and password for MongoDB, see this [How To Secure MongoDB on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-secure-mongodb-on-ubuntu-18-04)
>### Install PM2 Package for Process Management
To install, run the
```
npm install pm2
```

## Install and Run the Project on Our Ubuntu System
>### Clone the project from the GitHub repository
```
git clone <github:repo_url>
```
>### Configuration the environment
Open the .env file in the root directory
- Backend service runs on PORT:2083
```
PORT=2083
```
- Configration the Database service:  ***we use `crosmo` database***
```
MONGO_HOST=mongodb://username:password@hostname/crosmo
MONGO_PORT=27017
```
- Set JWT SECRET KEY for User Authentication
```
JWT_SECRET_KEY=your_secret_key
```
- Configure the variables for the web3 service
```
GATE_WAY=web3_provider_url
SHOOTER_CONTRACT=contract_address
PRIVATE_KEY=admin_wallet_private key
```
>### Install node modules
```
npm install --legacy-peer-deps
```
>### Management with PM2 package
```
pm2 start "npm run start:prodcution" --name "<your service name>"
```
>### Runnning the project
If you set the pm2 service, project will run the background
To see the process list, run the
```
pm2 list
```
To see the process logs, run the
```
pm2 logs <your service name>
```
If you want to restart the project, run the
```
pm2 restart  <your service name>
```