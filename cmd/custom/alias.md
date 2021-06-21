---
description: '"Alias" command type is used to invoke another built-in bot command.'
---

# Alias

{% hint style="warning" %}
Alias commands are working only for built-in JuniperBot commands. You can't create an alias for custom commands or commands of another bots.
{% endhint %}

## How it is useful? <a id="why"></a>

You can use this type of command to add an aliases to existent built-it bot commands.

## The behavior and settings <a id="settings"></a>

* The command content is a field where you should specify the name \(with parameters optionally\) of build-it command that you want to add an alias to.
* You shouldn't type prefix. If you change it, such command will stop working. 
* If built-in command involves interacting with some input parameters, write `{{arguments}}` in the command content after the command name. 
* The access rights of both commands will be checked. For example, if you set a allowed role in a custom command, and also set another allowed role in the command that is being redirected to, you will need to have both of these roles to execute such command.

## Example <a id="example"></a>

Let's say you need a command `!profile` worked exactly the same way as `!user`. To do this, you need:

1. Create a new custom command;
2. Select the "alias" command type;
3. In the command content enter the `user {{arguments}}`;
4. Save.

Note that we used `{{arguments}}` to pass all arguments to build-in command so the `!profile @SomeMember` would also work.

