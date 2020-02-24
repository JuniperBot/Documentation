---
description: >-
  You can use following variables in any message templates you can find in your
  server's dashboard.
---

# Template variables

These can be used by typing them inside:

* Message content;
* Embed's author;
* Embed's title;
* Embed's footer;
* Embed's fields \(both title and value\).

## Member

Variables set returning some useful info about member invoked related command or event \(ranking level up, etc\).

| Variable | Type | Description |
| :--- | :--- | :--- |
| `{member}` | Mention | Mention of member |
| `{member.id}` | Number | Member's unique identifier |
| `{member.mention}` | Mention | Mention of member |
| `{member.nickname}` | String | Server nickname of the member or his original name |
| `{member.name}` | String | Member's name |
| `{member.discriminator}` | String | Member's discriminator |
| `{member.joinedAt}` | [DateTime](data-types.md#datetime) | Member's joining date and time |
| `{member.createdAt}` | [DateTime](data-types.md#datetime) | Member's creation \(registration\) date and time |
| `{member.status}` | String | Status of the member with emoji icon. |
| `{member.avatarUrl}` | String | Member's avatar URL |
| `{member.level}` | Number | Member's ranking level |
| `{member.voiceTime}` | String | Time spent in voice channels |
| `{member.cookies}` | Number | Member's cookie count |

## Server

Variables set returning some useful info about your server.

| Variable | Type | Description |
| :--- | :--- | :--- |
| `{server}` | String | Server's name |
| `{server.owner}` | [Member](./#member) | Server's owner |
| `{server.id}` | Number | Server's unique identifier |
| `{server.name}` | String | Server's name |
| `{server.iconUrl}` | String | Server's icon URL |
| `{server.region}` | String | Server's region name with emoji icon |
| `{server.afkTimeout}` | Number | AFK Timeout of the voice channel \(in minutes\) |
| `{server.afkChannel}` | String | Name of AFK voice channel |
| `{server.memberCount}` | Number | Amount of members in your server |
| `{server.createdAt}` | [DateTime](data-types.md#datetime) | Server's creation date and time |

## Channel

Variables set returning some useful info about target channel of related message \(excluding DM's\).

| Variable | Type | Description |
| :--- | :--- | :--- |
| `{channel}` | Mention | Mention of channel |
| `{channel.id}` | Number | Channel's unique identifier |
| `{channel.name}` | String | Channel's name |
| `{channel.mention}` | Mention | Mention of channel |
| `{channel.topic}` | String | Channel's topic |
| `{channel.position}` | Number | Position of the channel in the list \(1 is the top of the list\) |
| `{channel.createdAt}` | [DateTime](data-types.md#datetime) | Channel's creation date and time |

## Ranking

Additional variables set used only in ranking level-up template.

| Variable | Type | Description |
| :--- | :--- | :--- |
| `{level}` | Number | Member's new level |

## Custom commands

Additional variables set used only in custom commands.

| Variable | Type | Description |
| :--- | :--- | :--- |
| `{content}` | String | Member's content typed with command, e.g. if `!command blablabla` invoked, the `{content}` will be `blablabla`. |

