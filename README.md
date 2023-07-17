<div align="center">
  <img src="https://i.imgur.com/o558Qnq.png" align="center">
  <br>
  <strong><i>A feature-rich Modmail bot for Discord.</i></strong>
  <br>
  <br>

  **This project is a fork of [kyb3r/modmail](https://github.com/kyb3r/modmail).**
  
  <a href="https://heroku.com/deploy?template=https://github.com/modmail-dev/modmail">
    <img src="https://img.shields.io/badge/deploy_to-heroku-997FBC.svg?style=for-the-badge&logo=Heroku">
  </a>

  <a href="https://github.com/modmail-dev/modmail/">
    <img src="https://api.modmail.dev/badges/instances.svg" alt="Bot instances">
  </a>

  <a href="https://discord.gg/cnUpwrnpYb">
    <img src="https://img.shields.io/discord/1079074933008781362.svg?label=Discord&logo=Discord&colorB=7289da&style=for-the-badge" alt="Support">
  </a>

  <a href="https://patreon.com/kyber">
    <img src="https://img.shields.io/badge/patreon-donate-orange.svg?style=for-the-badge&logo=Patreon" alt="Python 3.8">
  </a>

  <a href="https://www.python.org/downloads/">
    <img src="https://img.shields.io/badge/Made%20With-Python%203.8-blue.svg?style=for-the-badge&logo=Python" alt="Made with Python 3.8">
  </a>

  <a href="https://github.com/ambv/black">
    <img src="https://img.shields.io/badge/Code%20Style-Black-black?style=for-the-badge">
  </a>

  <a href="https://github.com/modmail-dev/modmail/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-agpl-e74c3c.svg?style=for-the-badge" alt="MIT License">
  </a>

<br>
<img src='https://i.imgur.com/fru5Q07.png' align='center' width=500>
</div>


## What is Modmail?

Modmail is similar to Reddit's Modmail, both in functionality and purpose. It serves as a shared inbox for server staff to communicate with their users in a seamless way.

This bot is free for everyone and always will be.

## How does it work?

When a member sends a direct message to the bot, Modmail will create a channel or "thread" into a designated category. All further DM messages will automatically relay to that channel; any available staff can respond within the channel.

Our Logviewer will save the threads so you can view previous threads through their corresponding log link. Here is an [**example**](https://logs.modmail.dev/example).

## Features

* **Highly Customisable:**
  * Bot activity, prefix, category, log channel, etc.
  * Command permission system.
  * Interface elements (color, responses, reactions, etc.).
  * Snippets and *command aliases*.
  * Minimum duration for accounts to be created before allowed to contact Modmail (`account_age`).
  * Minimum length for members to be in the guild before allowed to contact Modmail (`guild_age`). 

* **Advanced Logging Functionality:**
  * When you close a thread, Modmail will generate a log link and post it to your log channel.
  * Native Discord dark-mode feel.
  * Markdown/formatting support.
  * See past logs of a user with `?logs`.
  * Searchable by text queries using `?logs search`.

* **Robust implementation:**
  * Schedule tasks in human time, e.g. `?close in 2 hours silently`.
  * Editing and deleting messages are synced.
  * Support for the diverse range of message contents (multiple images, files).
  * Paginated commands interfaces via reactions.

This list is ever-growing thanks to active development and our exceptional contributors. See a full list of documented commands by using the `?help` command.

## Differences in this fork compared to vanilla Modmail

There are more changes planned, but this is what I have for now:

* Removal of scary server tracking feature
* Slightly more streamlined pip3 dependency management
* Mandatory opening message lengths
* Customizable confirm open thread timeout

## Installation

Q: Where can I find the Modmail bot invite link?

A: Unfortunately, due to how this bot functions, it cannot be invited. The lack of an invite link is to ensure an individuality to your server and grant you full control over your bot and data. Nonetheless, you can quickly obtain a free copy of Modmail for your server by following one of the methods listed below (roughly takes 15 minutes of your time).

There are a few options for hosting your very own dedicated Modmail bot.

You *can* host this bot on Heroku. You shouldn't do this; you should host your bot on a server - bare metal or VPS. I recommend using Docker but almost anything is better than Heroku. When I get a chance, I will write a guide for that. If you understand the risks, here's how to use Heroku anyway:

Installation via Heroku is possible with your web browser alone. 
Upstream's [**installation guide**](https://github.com/kyb3r/modmail/wiki/Installation) (which includes a video tutorial!) will guide you through the entire installation process.

When using Heroku, you can configure automatic updates:
 - Login to [GitHub](https://github.com/) and verify your account.
 - [Fork this repo](https://github.com/antigravities/modmail/fork).
 - Install the [Pull app](https://github.com/apps/pull) for your fork. 
 - Then go to the Deploy tab in your [Heroku account](https://dashboard.heroku.com/apps) of your bot app, select GitHub and connect your fork (usually by typing "Modmail"). 
 - Turn on auto-deploy for the `master` branch.

### Locally

I will write a better guide for this soon, but upstream's gist is fairly accurate:

Local hosting of Modmail is also possible. First, you will need [`Python 3.7`](https://www.python.org/downloads/release/python-37).

Follow upstream's [**installation guide**](https://github.com/kyb3r/modmail/wiki/Installation) and disregard deploying the Heroku bot application. 

Clone the repo:

```console
$ git clone https://github.com/antigravities/cutemail
$ cd modmail
```

Install dependencies:

```console
$ python3 -m pip install -r requirements.min.txt
# or, with pipenv
$ pipenv install
```

Rename the `.env.example` to `.env` and fill out the fields. If `.env.example` is nonexistent (hidden), create a text file named `.env` and copy the contents of [`.env.example`](https://raw.githubusercontent.com/antigravities/cutemail/master/.env.example) then modify the values.

Finally, start Modmail.

```console
$ python3 bot.py
# or, with pipenv
$ pipenv run bot
```

#### Docker

This repo will Soon&trade; supply a Dockerfile for simplified deployment. 

For now, you can build your own Docker image:

```console
$ docker build . --tag=modmail
```

And then to run it:
```console
$ docker run --env-file .env modmail
```

<!-- 
Or run directly from a pre-built version from https://hub.docker.com/.

- Kyber's:

```console
$ docker pull kyb3rr/modmail
```

And to run your docker image:

```console
$ docker run --env-file .env kyb3rr/modmail
``` -->
- `.env` should be the path to your env file; you can also supply a path: `/path/to/.env`.

## Plugins

Modmail supports the use of third-party plugins to extend or add functionalities to the bot.
Plugins allow niche features as well as anything else outside of the scope of the core functionality of Modmail. 

You can find a list of third-party plugins using the `?plugins registry`  command or visit upstream's [Unofficial List of Plugins](https://github.com/kyb3r/modmail/wiki/Unofficial-List-of-Plugins) for a list of plugins contributed by the community.

To develop your own, check out upstream's [plugins documentation](https://github.com/kyb3r/modmail/wiki/Plugins).
