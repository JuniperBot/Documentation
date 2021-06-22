---
description: Message Templates and Template Engine.
---

# Message Templates

## What is it and why we need it? <a id="why"></a>

Message Templates are special message constructors and editors for commands, notifications, reminders and a lot of other stuff that you can find in [server's dashboard](../../#configure). Each of them can contain some message related information that you can insert in the right places using special markup language that our built-in template engine offers.

## Message Template Structure <a id="structure"></a>

Structure of all Message Templates is mostly the same on the whole system, check the [User Interface](ui.md) article.

Message Templates are used in the features like:

* Notifications;
* Level up announcements;
* Custom Commands;
* Auto-Moderation announcements.

JuniperBot sequentially processes all template fields in the following order:

1. Message Content Template;
2. Embed Content Template
3. Embed's Author values;
4. Embed's Title values;
5. Embed's Footer values;
6. Embed's Fields \(both name and value\).

## What should we do with this? <a id="what-do"></a>

Template Engine of the JuniperBot is very powerful tool and requires some programming skills to understand it.

If you are not fimiliar those things, welcome to the [Beginners](beginners/) article.

If you're brave enouth and ready to familiarize yourself with the power of the template engine, welcome to the [Advanced](advanced/) article.

