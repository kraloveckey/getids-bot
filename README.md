# GetIDsBot

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/kraloveckey)

[![Telegram Channel](https://img.shields.io/badge/Telegram%20Channel-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/cyber_notes)

## Introduction.

GetIDsBot is a chatbot for the Telegram Messaging Plattform which main purpose
is to extract useful informations from messages that are normally hidden and
to enhance them. This means...

- converting file_sizes and durations to human readable formats.
- interpolating account creation dates from the users chat_id.
- displaying it all [tree(1)'ish'](<https://en.wikipedia.org/wiki/Tree_(command)>).

## Using this bot. Host one yourself.

You will need a bot token from the [BotFather](https://t.me/botfather) and a server with nodejs and npm installed to run it. 
Yes, bots are programs and they must run on some computer.

## Account creation dates.

Most people want to use this, so here is a bit of explanation for all of you:
Telegram gives each chat (that is users, bots, groups and channels) a globally
unique numerical id. These id numbers aren't given out sequentially, so two users
signing up at the exact same time will probably have a difference of up to a few
millions. Two possible reasons are:

- Sharding: Telegram registrations won't all happen on the same server. To avoid
  giving out the same id twice, all registration servers reserve a range of ids
  from the central registry and periodically fetch new ones.
- Obfuscation: You should not be able to guess the signup date from one's id.

This is still speculation, and we don't know for certain, but averaged out over
a year or so, the IDs do still increase. There are some exceptions, but guessing
is still possible.

We collected a bunch of ids for which we knew the rough creation dates, anonymized
the dates and used some dark magic called "maths" to estimate a creation date.

## Setup

- Clone repository.
- Run `npm install` into repository directory.
- Run `node index.js` or create the systemd.service <code>bot-getid.service</code>.