---
layout: default
---

# Features

Currently there is only a pushbot available. Continue reading to see what it is and how to use.

## Pushbot

Inspired by [Server Chan][ServerChan], the `/push` command acts as a tool for programmers / server operators to easily push instant messages to themselves by performing an HTTP POST request.
For example, a server operator can write a simple script to monitor the server status, and push an alert message to himself about abnormal service status. Thanks to Telegram, this push is nearly instant; But due to implement detail (a POST request is first queued by the bot before being pushed to Telegram, this is for performance consideration), the message is slightly delayed. Currently the delay is about 1~3 seconds.

### Pushbot usage

Just search for `eth0_bot` in Telegram, or simply click [here][eth0_bot], and start chatting with the bot. Send `/push` to her and she will answer you with the help about the pushbot.

#### How does it work

1. You register with [eth0_bot][eth0_bot] and she returns a unique ID (push code) representing the chat between you and her;
2. You send an HTTP request containing the unique ID and the content you want to push;
3. The bot recognize the chat with given ID, and send the given content back to that chat;

You might want to revoke the registered code and register a new one when:

* You lost you code;
* You think someone else **might have** it;
* You're receiving messages that aren't sent under your control (which means someone else **has** your code);
* You just want to, for no reason;

#### API reference

* `POST` `/push`

  Parameters:
    * `code`: **required**, your push code, as told by the bot via Telegram after sending `/register` to her;
    * `text`: **required**, the text to push;
    * `parse_mode`: optional, specify the content format of `text`, could be one of the following:
      * `markdown`: this is the default value;
      * `html`: instruct the bot to send `text` as HTML content;
      * `plain`: instruct the bot to send `text` as plain text content;
      Notice: if your content might be valid markdown or HTML content, you should explicitly use `plain`, or Telegram server will refuse to accpet it, resulting the push failed.
* `GET` `/push/<your_push_code_here>?text=<your_text_to_push>&parse_mode=<content_parse_mode>`

  If you don't want to set `parse_mode`, drop the `&parse_mode=...` part.

### Why not just use Server Chan?

If you're in China or you speak Chinese, and Server Chan works well on your phone, I suggest you keep using it.
While Server Chan is indeed very good, there are some problems. Server Chan push messages to you via its client app, or via a WeChat account. First of all I don't want another new app, especially for such a simple work (besides, there was issue with long-live connection when I first used it); Secondly WeChat for Android is very slow, and cause both performance and battery issues on my phone. Telegram is a lightweight alternative to both: it's fast, focuses on only one thing -- messaging, and it's secure.

# Changelog

See [changelog page][Changelog] for detailed log.

# Terms of service

See [Terms of service page][ToS] for the up-to-date version of our terms.

[ServerChan]: http://sc.ftqq.com/2.version
[eth0_bot]: https://telegram.me/eth0_bot
[Changelog]: changelog
[ToS]: terms
