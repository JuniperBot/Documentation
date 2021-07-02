# Frequently Asked Questions

## Music is lagging and stuttering. How to fix that?

This issue can be cause by the following reasons:

* **Music servers under high load:** You can find current music servers load in the playback message or on the [Statistics](https://juniper.bot/status) page. If the load less than 80%, it is not an issue. 
* **Connection issues to Discord voice gateway or its high load:** There is a network unit between you and the bot called a voice gateway. Discord has a lot ot them tied to the Region selected in the voice channel settings. The issue may be between the gateway and the bot, or between you and this gateway. Try changing the region of the voice channel and see if the things got improved \(do not forget to completely restart the music playback\). 
* **Сonnection issues to the music source:** Beyond our control could be a connection issues to the music source \(YouTube, Yandex.Music, radio stations\) so the music source itself is under high load or the connection is unstable. The issues may be either temporary or permanent and this could happen for radio stations basicaly. Unfortunately, we are not a huge company and we cannot have a music servers in every part of the world to provide a stable connection to everything. If this happens, try changing the radio station, use YouTube instead of Yandex.Music, or vice versa.

## What permissions are required to access server's dashboard?

[Server's dashboard](../#configure) is only available for server owner and the members with Administrator permission in their roles.

{% hint style="warning" %}
Note that any of those members can modify anything in server's dashboard. He could even manage to get the roles higher than his own.
{% endhint %}

## What is cookie box in member's rank and profile?

It is just a karma or reputation system, a simple counter that you can increment:

1. `@mention` member with cookie 🍪 emoji in the message. For example: `@NicePerson#1234 :cookie:`
2. Add 🍪 reaction to message of desired member.

{% hint style="info" %}
 One member can give the 🍪 to another **only once within 10 minutes**.
{% endhint %}

## What is Cluster and Shard?

Shard is a part of JuniperBot which handles specific portion of servers.  
Cluster is physical server instance handling specific portion of shards.

## Can we play bot's playlist again and how to do that?

 [Supported users](https://juniper.bot/donate) can do that using `!play` command with playlist link specified.

```text
!play https://juniper.bot/playlist/99eb328f-d970-4265-ae6f-07c1d7ac8682
```

Playlist links are always available at playback messages.

## Will be any economic system implemented here?

Will not. At all. **Never.** Use another bots who are originally designed for economic systems.

## How to calculate EXP required for level?

Check the [Ranking experience](../features/ranking/experience.md) article.

## How to limit commands to work only in certain channels or for certain members?

Check the [Custom Commands](../cmd/custom/#interface) article. Access settings are suitable for build-in commands as well.



