Ybot
===============

Ybot is a customizable bot which was inspired by GitHub's
[Hubot](http://hubot.github.com/). Hubot is really cool, but sorry, I
don't like JavaScript and I don't know coffescript. Ybot is completely
written in Erlang/OTP and you can write plugins in Python, Perl, Ruby,
or even in shell.

[![Build Status](https://travis-ci.org/0xAX/Ybot.png)](https://travis-ci.org/0xAX/Ybot)

[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user\_id=0xAX&url=https://github.com/0xAX/Ybot&title=Ybot&language=&tags=github&category=software)

This branch
===========

This is a stable version of [My Ybot fork](https://github.com/manpages/Ybot)
that is tested to work with IRC.

Features
=========

  * Completely written in Erlang;
  * Simultaneously run any number of bots on different transports;
  * Supports plugins in different technology;
    * Python plugins;
    * Ruby plugins;
    * Shell plugins;
    * Perl plugins;
    * Elixir plugins;
  * You don't need to know Erlang to write a plugin;
  * Command history with tunable limit;
  * Dynamic loading of plugins;
  * Very easily extensible;
  * Supports IRC and IRC via SSL;
  * Supports XMPP;
  * Supports Campfire
  * HTTP interface;

Building and Running
=====================

First of all you must get your own Ybot:

```
git clone https://github.com/0xAX/Ybot.git
```

Or download the source file archive: [.tar.gz](https://github.com/0xAX/Ybot/tarball/master) or [.zip](https://github.com/0xAX/Ybot/zipball/master)

After getting source you need to download dependencies and build the source:

```
./rebar get-deps && ./rebar compile
```

Then edit the `ybot.config` configuration file and you can run your Ybot copy:

```
./start.sh
```

Dependencies
=============

  * [lager](https://github.com/basho/lager) - A logging framework for Erlang/OTP.
  * [reloader](https://github.com/bjnortier/reloader) - Mochiweb's reloader.
  * [ibrowse](https://github.com/cmullaparthi/ibrowse) - Erlang http client.
  * [mochijson2](https://github.com/bjnortier/mochijson2) - Erlang json encoder/decoder.

Transport
==========

Ybot's basic transport is a network interface. Ybot is a chat bot and he
spends all of his life chatting. Ybot receives chat messages and execute
commands depending on those received messages. At that moment Ybot
supports:

  * IRC.
  * XMPP MUC.
  * Campfire.
  * HTTP.

Plugins
==========

Ybot is a chat bot and it can execute different commands. Commands are
simple chat messages. For example, a chat session:

```
you: Ybot math 1 + 5
Ybot: Answer: 6
```

Here are a few simple rules for structuring Ybot plugins.

  * You must address messages to the `Ybot`.

  * After addressing the bot you specify the command to be executed, for example `math` or `ping`. Every command consists from one word.

  * After the command you can specify arguments. Ybot sends all arguments in '' and it turns them into one argument. 

  * One command = One plugin. Plugins must live in the `plugins` directory.

  * Each plugin must have the correct extension, for example:

    * .py
    * .rb
    * .shell

Containing Python, Ruby or shell code.

  * The name of the plugin file must be the same name as the command.
    For example if we have a `Ybot ping` command, we must have a plugin
    named `ping.py` or `ping.rb` or `ping.shell`, etc.

  * Plugin can consist of any code but write the results to `STDOUT` in the end.

Example Ybot:

```
Ybot math 3 ^ 2
```

Here Ybot calls the `math` plugin with the argument: '3 ^ 2'

Current plugins
================

  * chuck - Chuck Norris quotes :)
  * decide - Ybot try to help make decisions for you.
  * github_status - Github status state.
  * help - Ybot help.
  * ping - Ybot simple ping/pong.
  * math - Ybot calculate math expressions.
  * date - Ybot show date/time.
  * pugme - Ybot pugme service plugin.
  * erl   - Ybot computation of erlang expression using tryerlang.org.
  * today? - Ybot return current day.
  * shorten_url - Ybot url shortener with goo.gl.
  * hacker_news - Ybot download news from https://news.ycombinator.com/
  * wat - Ybot random WAT image
  * check-site - Ybot check site up/down state
  * ruby - Ybot eval simple ruby expression
  * ip - Ybot external ip
  * hacker_help - Ybot search in stackoverflow.

These are Ybot's core plugins. You can find other plugins at [ybot-contrib](https://github.com/0xAX/ybot-contrib)

Contribute
============

Ybot is an open source project under the Erlang public license (see LICENSE file). Issues, questions and patches are welcome.

If you're hacking Ybot core, please, before sending your pull request,
pull and merge Ybot master to avoid conflicts.

  * Fork main ybot repository (https://github.com/0xAX/Ybot).
  * Make your changes in your clone of ybot.
  * Test it.
  * Send pull request.

Author
========

[@0xAX](https://twitter.com/0xAX)
