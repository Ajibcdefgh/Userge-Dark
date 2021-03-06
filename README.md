<p align="center">
    ![logo](https://telegra.ph/file/09d56c909d5193ff3434e.jpg)
    </a>
    <br>
    <b>Pluggable Telegram UserBot</b>
    <br>
    <a href="https://github.com/Ajibcdefgh/Userge-Dark#inspiration-">Inspiration</a>
    &nbsp•&nbsp
    <a href="https://github.com/Ajibcdefgh/Userge-Dark#features-">Features</a>
    &nbsp•&nbsp
    <a href="https://github.com/Ajibcdefgh/Userge-Dark#example-plugin-">Example</a>
    &nbsp•&nbsp
    <a href="https://github.com/Ajibcdefgh/Userge-Dark#requirements-">Requirements</a>
    &nbsp•&nbsp
    <a href="https://github.com/Ajibcdefgh/Userge-Dark#project-credits-">Project Credits</a>
    &nbsp•&nbsp
    <a href="https://github.com/Ajibcdefgh/Userge-Dark#copyright--license-">Copyright & License</a>
</p>

# Userge 🔥

[![Build Status](https://travis-ci.com/Ajibcdefgh/Userge-Dark.svg?branch=alpha)](https://travis-ci.com/Ajibcdefgh/Userge-Dark)
![Python Version](https://img.shields.io/badge/python-3.8-lightgrey)
![Release](https://img.shields.io/github/v/release/Ajibcdefgh/Userge-Dark)
![Stars](https://img.shields.io/github/stars/Ajibcdefgh/Userge-Dark)
![Forks](https://img.shields.io/github/forks/Ajibcdefgh/Userge-Dark)
![Issues Open](https://img.shields.io/github/issues/Ajibcdefgh/Userge-Dark)
![Issues Closed](https://img.shields.io/github/issues-closed/Ajibcdefgh/Userge-Dark)
![PRs Open](https://img.shields.io/github/issues-pr/Ajibcdefgh/Userge-Dark)
![PRs Closed](https://img.shields.io/github/issues-pr-closed/Ajibcdefgh/Userge-Dark)
![Contributors](https://img.shields.io/github/contributors/Ajibcdefgh/Userge-Dark)
![Repo Size](https://img.shields.io/github/repo-size/Ajibcdefgh/Userge-Dark)
![License](https://img.shields.io/github/license/Ajibcdefgh/Userge-Dark)
![Commit Activity](https://img.shields.io/github/commit-activity/m/Ajibcdefgh/Userge-Dark)
[![Plugins Repo!](https://img.shields.io/badge/Plugins%20Repo-!-orange)](https://github.com/UsergeTeam/Userge-Plugins)
[![Join Channel!](https://img.shields.io/badge/Join%20Channel-!-red)](https://t.me/theUserge)
[![DeepSource](https://static.deepsource.io/deepsource-badge-light-mini.svg)](https://deepsource.io/gh/Ajibcdefgh/Userge-Dark/?ref=repository-badge)
[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/Ajibcdefgh/Userge-Dark)

> **Userge** is a Powerful , _Pluggable_ Telegram UserBot written in _Python_ using [Pyrogram](https://github.com/pyrogram/pyrogram).

## Inspiration 😇

> This project is inspired by the following projects :)

* [tg_userbot](https://github.com/watzon/tg_userbot) ( heavily ) 🤗
* [PyroGramUserBot](https://github.com/SpEcHiDe/PyroGramUserBot)
* [Telegram-Paperplane](https://github.com/RaphielGang/Telegram-Paperplane)
* [UniBorg](https://github.com/SpEcHiDe/UniBorg)

> Special Thanks to all of you !!!.

## Features 😍

* Powerful and Very Useful **built-in** Plugins
  * gdrive [ upload / download / etc ] ( Team Drives Supported! ) 🤥
  * zip / tar / unzip / untar / unrar
  * telegram upload / download
  * pmpermit / afk
  * notes / filters
  * split / combine
  * gadmin
  * plugin manager
  * ...and more
* Channel & Group log support
* Database support
* Build-in help support
* Easy to Setup & Use
* Easy to add / port Plugins
* Easy to write modules with the modified client

## Example Plugin 🤨

```python
from userge import userge, Message, filters

LOG = userge.getLogger(__name__)  # logger object
CHANNEL = userge.getCLogger(__name__)  # channel logger object

# add command handler
@userge.on_cmd("test", about="help text to this command")
async def test_cmd(message: Message):
   LOG.info("starting test command...")  # log to console
   # some other stuff
   await message.edit("testing...", del_in=5)  # this will be automatically deleted after 5 sec
   # some other stuff
   await CHANNEL.log("testing completed!")  # log to channel

# add filters handler
@userge.on_filters(filters.me & filters.private)  # filter my private messages
async def test_filter(message: Message):
   LOG.info("starting filter command...")
   # some other stuff
   await message.reply(f"you typed - {message.text}", del_in=5)
   # some other stuff
   await CHANNEL.log("filter executed!")
```

## Requirements 🥴

* Python 3.8 or Higher 👻
* Telegram [API Keys](https://my.telegram.org/apps)
* Google Drive [API Keys](https://console.developers.google.com/)
* MongoDB [Database URL](https://cloud.mongodb.com/)

## UserGe MODES 🕹

* **USER** mode `(using user account)`
* **BOT** mode `(using bot account)`
* **DUAL** mode `(using both user and bot account)`

  > further **read** [config.env.sample](https://github.com/UsergeTeam/Userge/blob/alpha/config.env.sample)

## How To Deploy 👷

* With Heroku:
  > **NOTE** : your can fill other vars as your need and they are optional. (settings -> reveal config vars)
  * First click [**this**](https://heroku.com/deploy?template=https://github.com/UsergeTeam/Userge/tree/master)
  * Fill `API_ID`, `API_HASH`, `DATABASE_URL` and `LOG_CHANNEL_ID` (**required**)
  * Choose your [**MODE**](https://github.com/UsergeTeam/Userge#userge-modes-)
  * Then fill other **non-required** vars as relevent to your **MODE**
  * Finally **hit deploy** button

* With Docker 🐳 
    - [**See Detailed Guide**](resources/radmeDocker.md)

* With Git, Python and pip 🔧
  ```bash
  # clone the repo
  git clone https://github.com/UsergeTeam/Userge.git
  cd Userge

  # create virtualenv
  virtualenv -p /usr/bin/python3 venv
  . ./venv/bin/activate

  # install requirements
  pip install -r requirements.txt

  # Create config.env as given config.env.sample and fill that
  cp config.env.sample config.env

  # get string session and add it to config.env
  bash genStr

  # finally run the Userge ;)
  bash run
  ```

* **[More Detailed Guide](https://docs.google.com/document/d/15uoiOn2NkN518MMkx9h5UaMEWMp8aNZqJocXvS0uI6E)** 📝

### Video Tutorial 🎥

  [![Tutorial](resources/tutorial.jpg)](https://youtu.be/M4T_BJvFqkc "Tutorial")

### Support & Discussions 👥

> Head over to the [Discussion Group](https://t.me/usergeot) and [Update Channel](https://t.me/theUserge)

### Project Credits 💆‍♂️

* [Specially to these projects](https://github.com/UsergeTeam/Userge#inspiration-) 🥰
* [@uaudIth](https://t.me/uaudIth)
* [@K_E_N_W_A_Y](https://t.me/K_E_N_W_A_Y)
* [@nawwasl](https://t.me/nawwasl)
* [@TharukaN97](https://t.me/TharukaN97)
* [@Supun97](https://t.me/Supun97)
* [@gotstc](https://t.me/gotstc)

### Copyright & License 👮

* Copyright (C) 2020 by [UsergeTeam](https://github.com/UsergeTeam) ❤️️
* Licensed under the terms of the [GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007](https://github.com/UsergeTeam/Userge/blob/master/LICENSE)
