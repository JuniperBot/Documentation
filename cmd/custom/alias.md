---
description: '"Alias" command type is used to invoke another built-in bot command.'
---

# Alias

{% hint style="warning" %}
Redirection works only inside JuniperBot and only on built-in commands. You can't create a redirect to another bot's command.
{% endhint %}

## How it is useful? <a id="why"></a>

You can use this type of command to add an aliases to existent built-it \(i.e. not custom\) bot commands.

## The behavior and settings <a id="settings"></a>

* The command content is a field where you need to enter the name of another bot command that you want to add an alias to. 
* It is not recommended to enter prefix before the command in the content, because when you change it, such commands will stop working. 
* If built-in command involves interacting with some text written after the command, write `{content}` in the command content after the command name. 
* The "permissions and execution" of both commands are summed up. For example, if you set a allowed role in a custom command, and also set another allowed role in the command that is being redirected to, you will need to have both of these roles to execute such command.

## Creating a command with the "alias" type <a id="creating"></a>

Let's say you need a command `!helpme` worked exactly the same way `!help`. To do this, you need:

1. Create a new custom command;
2. Select the "alias" command type;
3. In the command content, write the name of the command that is being redirected to;
4. Save.

