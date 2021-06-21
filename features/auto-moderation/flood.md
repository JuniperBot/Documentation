---
description: >-
  Repeated Text Filter — triggers to specified amount of equal messages (flood)
  from the same member.
---

# Repeated Text

## Behaviour and Settings <a id="behaviour"></a>

* **Amount of Identical Messages** — maximum number of identical messages allowed;
* **Sequential messages only** — if checked, the filter will only trigger on identical messages that are written one after another and were not interrupted by any other message from this member. For example, filter will trigger on "a, a, a, a, a", but will not trigger on "a, a, b, a, a";
* **Reset flood counter on hit** — if checked, the flood counter will be reset each time it triggered. For example, if there is a limit of 5 identical messages, as well as the option is not active, the filter will trigger for each subsequent identical message \(5th, 6th, 7th, etc\). If the option is active, the member will need to send 5 more identical messages for the filter to trigger again;

{% hint style="warning" %}
The flood counter is valid for 15 minutes.
{% endhint %}

{% hint style="info" %}
You can find available template variables for notification message template [here](../message-templates/advanced/types.md).
{% endhint %}

