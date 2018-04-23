# GarlicoinDiscordBot
A NodeJS-based Discord bot for Garlicoin Pool Servers

This bot requires a Node server with the following `npm` packages installed:
```
Discord.js http https fs
```
You will also need to visit the [Discord App Portal](https://discordapp.com/developers/docs/intro) to create an app with an App Bot User account and to get the token used for connecting to the Discord network with [DiscordJS](https://discord.js.org). 

## Configuration
A configuration file `config.json` is included with the package. Use the following guide to determine how you should populate it:
|Key|Description|
|-|-|
|token|The Discord App token you generate at the Discord App Portal|
|name|The name your bot will take when it connects|
|server_name|The name of your Garlicoin Pool server - this is presented to new members when they are greeted by the bot|
|pool_codebase|The codebase your Garlicoin Pool is running on. Currently only `NOMP` is supported.|
|pool_api_url|The URL to your pool's API|
|prefix|Define the prefix you would prefer for bot commands (Default is `!`)|
|bot_admin_roles|Any roles (separated by spaces) you would like to have access to Bot Admin Commands|

## Execution
Use `node bot.js` within the deployment directory to start the bot. If all is configured correctly you should see it join your server. You can then go about managing roles. 

I prefer to use the `NPM` package `Forever` to keep the bot running at all times. However, you can handle it however you prefer.


## Bot Admin Commands
The bot aslo has some commands limited to Admin-level users (defined in `config.json` under the `bot_admin_roles` definition) only. When you use any of these commands the bot will delete your request statement. The commands are defined as follows:
|Command|Result|
|-|-|
|echo|This will cause the bot to repeat what you've stated after the command. For example `!echo Hello!` will cause the bot to send `Hello!` to the channel.|
|broadcast|This is the same as `echo` but it will be sent to *all channels* the bot is currently connected to.|
|save|This will cause the bot to write out any JSON data it has. Useful at times if you want to ensure any configuration changes or member updates are properly saved. *This command is here as a convenience but should rarely be necessary.*|

## Bot User Commands
The bot has a standard `help` command that should help you and any members of your server understand how to utilize the bot.