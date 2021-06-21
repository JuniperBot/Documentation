---
description: Caps Lock Filter — triggers to excessive CAPS LOCK in messages.
---

# Caps Lock

## Behaviour and Settings <a id="behaviour"></a>

* **Minumum Amount of Letters** — allows you to set how short messages will be affected by the filter. Do not set this value too low to avoid false positives \(you do not want the bot to punish for the message "Ok" if you specify the minimum amount of 2 with a percentage of 50%, right?\);
* **Uppercase Percent** — maximum allowable percentage of UPPER case letters in a message;

{% hint style="warning" %}
The filter does not take into account uppercase characters of emotions or mentions, but inside links as well.
{% endhint %}

{% hint style="info" %}
You can find available template variables for notification message template [here](../message-templates/advanced/types.md).
{% endhint %}

