# Hackbot

This is a slackbot, using [Botkit](http://howdy.ai/botkit) as a starting point.

## Purpose

The bot was quickly slapped together to be used during a demonstration or hackathon.  It aims to teach the security principle of never trusting user input.  Many junior developers are aware of the dangers of inputs when it comes to common attack vectors such as SQL queries and XSS, but they don't always think to sanitize input in other scenarios.

## Hacking the bot

This bot is designed to run on a Windows system and offer help on the syntax for using Windows cmd.exe shell commands such as "dir", "rd", etc.  (See next section if you want to change it for another O/S).  If you type "cmdhelp dir" to the bot it will reply back with info on how to use the dir command.

With some malicious input, it's easy to make the bot run arbitary commands and programs on the Windows machine that hosts it.  Hint: It doesn't seem susceptible to "&&" but it's far from foolproof.  Try make the bot execute the shell command "whoami" to prove the point, and try to resist the urge from deleting the family photos stored on the bot's Windows host machine...

Note: The slackbot works by connecting to a WebSocket in the slack cloud, so it can be hosted on your laptop and doesn't need to be exposed publicly over the Internet.

## Non-Windows users

It would be a trivial 1-line code change to change the bot to function on a macOS or Linux host instead.  It should just be a matter of changing "help" to "man" on line 109 of slack_bot.js.
