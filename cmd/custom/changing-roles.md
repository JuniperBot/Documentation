---
description: '"Changing roles" command type is used for adding or removing roles.'
---

# Changing Roles

## How it is useful? <a id="why"></a>

You can use this command to let the member's add or remove certain roles for themselves. For example, color roles or roles that allow access to certain channels. Everything is limited only by your imagination.

## The Behavior and settings <a id="settings"></a>

* The bot cannot add or remove roles that are higher in the roles hierarchy than its own roles. 
* In order for the bot to let modify member's roles, bot must be granted "Manage roles" permission. 
* The "Modify roles of @mentioned member" checkbox will allow to perform roles modification not just for themselves, but for any mentioned member too.

{% hint style="warning" %}
If you use the command to assign roles to @mentioned members, be sure to configure its access rights for your own use-case, otherwise anyone can access the roles specified in the command.
{% endhint %}

## Example <a id="example"></a>

A few simple steps:

1. Create a new custom command;
2. Select the "changing roles" command type;
3. Select the roles to add or remove;
4. Save.

