---
description: You can create your own commands that can perform certain actions.
---

# Custom Commands

Custom commands can be created and configured at the [server's dashboard](../../#configure) in the tab called "custom commands". You can disable any custom command if necessary and configure the necessary access rights in the same way as the built-in bot commands.

## Settings Interface <a id="interface"></a>

Each command has a certain set of general settings regardless of its type:

![General settings Interface](../../.gitbook/assets/oaoaommm-20-04-15-18-05-16.png)

* **Command** — the name of the command that will be used to invoke it in Discord;
* **Type** — type of command. You can find detailed explaination for each of them just below in next sections within this category;
* **Short description** — just a short description of this command. It will be displayed in the list of custom commands, as well as in the help command in the Discord;
* **Allowed/ignored roles and channels** — access rights to commands by roles and channels.

## Command Types <a id="command-types"></a>

1. **Message** — invocation of such will result in simple response with specified text or embed. 
2. **Alias** — invocation of such command will be redirected to another build-in command specified in the body of this custom command. For example, if you create a command with the name `me`, enter the `user` in the body, invocation of `!me` will be similar to invocation the built-in command `!user`. Redirection only works on the bot's built-in commands!
3. **Changing Roles** — invocation of such command will remove or add the roles specified in the command settings. By default, this can only be done by the member who called this command.

