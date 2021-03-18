# Juanbottelegram
using Botfather telegram api

***you must request the token in the botfather user of telegram***

To start make the project we must execute the following command:

```
 {
   "name": "test-bot",
   "version": "1.0.0",
   "description": "Bot para telegram en nodejs",
   "main": "bot.js",
   "scripts": {
     "test": "echo \"Error: no test specified\" && exit 1"
   },
   "author": "Juan Obregon",
   "license": "ISC"
 }

```

## Modify the "package.json".

Once automatically generating the "package.json" we have to make a modification that is not mandatory but it is convenient in the "scripts" section as it serves us to establish start commands for our bot, in this case we create a command called "start" within the scripts section of the json that executes the index.js file (we will create it later). The result of the modification should be similar to the following:

```
{
   "name": "test-bot",
   "version": "1.0.0",
   "description": "Bot para telegram en nodejs",
   "main": "bot.js",
   "scripts": {
     "start": "node index.js"
   }
   "author": "Juan Obregon",
   "license": "ISC"
 }
```
*This allows us that instead of having to write in the terminal "node index.js" we can write "npm start" obtaining the same result.*

 ## Installation of the node-telegram-bot-api library
-Once we have finished editing the "package.json" file we proceed to install a library written in NodeJS that will allow us to create Telegram bots using this same language. Its installation is really simple, we just need to run the following command in the console:

```
npm install --save node-telegram-bot-api

```

*Once we have this we create a file called bot.js or whatever you want to call it. If you call it index.js you will not have to modify the package.json, otherwise in the Scripts section replace index.js with the name of the .js file you created. Inside this file we are going to put the whole bot program:*
```
// Import the node-telegram-bot-api library 
const TelegramBot = require('node-telegram-bot-api');


// We create a constant that stores the token of our Telegram bot that we have previously created from the @BotFather bot.


const token = 'Introduce-the-API-KEY';

// Create a bot that uses 'polling' to fetch new updates
const bot = new TelegramBot(token, {polling: true});

// ⚠️ After this comment is where we put the logic of our bot where we can create the commands and events to give functionalities to our bot

// Implementation of the first functionality: When we send the message "Hello" it recognizes your name and generates an input like "Hello Juan!".

bot.onText(/^\hola/, (msg) => {
     bot.sendMessage(msg.chat.id, "Hola  " + msg.from.first_name);
 });
```
To execute the bot once we have the bot.js file configured we only have to put in the terminal:
```
npm start
```




