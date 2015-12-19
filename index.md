---
layout: default
---

# Features

Currently there is only a pushbot available. Continue reading to see what it is and how to use.

## Pushbot

Inspired by [Server Chan][ServerChan], the `/push` command acts as a tool for programmers / server operators to easily push instant messages to themselves by performing an HTTP POST request.
For example, a server operator can write a simple script to monitor the server status, and push an alert message to himself about abnormal service status. Thanks to Telegram, this push is nearly instant; But due to implement detail (a POST request is first queued by the bot before being pushed to Telegram, this is for performance consideration), the message is slightly delayed. Currently the delay is about 1~3 seconds.

### Pushbot usage

Just search for `eth0_bot` in Telegram, or simply click [here][eth0_bot], and start chatting with the bot. Send `/push` to her and she will answer you with detailed help about the pushbot.

### Why not just use Server Chan?

If you're in China or you speak Chinese, and Server Chan works well on your phone, I suggest you keep using it.
While Server Chan is indeed very good, there are some problems. Server Chan push messages to you via its client app, or via a WeChat account. First of all I don't want another new app, especially for such a simple work (besides, there was issue with long-live connection when I first used it); Secondly WeChat for Android is very slow, and cause both performance and battery issues on my phone. Telegram is a lightweight alternative to both: it's fast, focuses on only one thing -- messaging, and it's secure.

# Changelog

See [changelog page][Changelog] for detailed log.

[ServerChan]: http://sc.ftqq.com/2.version
[eth0_bot]: https://telegram.me/eth0_bot
[Changelog]: changelog