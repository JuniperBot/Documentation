---
description: General variables for most of Message Templates
---

# Variables

### Common Variables <a id="common"></a>

Message Templates have some common predefined variables:

| Variable | Type | Description |
| :--- | :--- | :--- |
| `guild` | ​[Guild](types.md#guild)​ | Server information |
| `bot` | ​[Member](types.md#member)​ | Member instance of JuniperBot itself |
| `member` | ​[Member](types.md#member)​ | Member instance related to this template |
| `channel` | ​[TextChannel](types.md#textchannel)​ | Target channel where this template should be sent \(if only guild message, not DMs\) |
| `sourceChannel` | ​[TextChannel](types.md#textchannel)​ | Source channel like the channel where the custom command were invoked. It is different from `channel` that the last one may be different target channel selected in the message template interface. |
| `message` | ​[Message](types.md#message)​ | Message instance related to this template. For example, custom command invocation message or violation message in Auto-Moderation. |

Those variables are always included in every message template. Sections below will describe some additional variables for a different message templates.‌

### Member Ranking <a id="ranking"></a>

Level up announcement message template has some additional variables:

| Variable | Type | Description |
| :--- | :--- | :--- |
| `rolesAdded` | [List](syntax/expressions.md#lists)&lt;[Role](types.md#role)&gt; | List of role-rewards added |
| `rolesRemoved` | [List](syntax/expressions.md#lists)&lt;[Role](types.md#role)&gt; | List of role-rewards removed |

### Auto-Moderation <a id="automod"></a>

These variables are used in Auto-Moderation Filters for violation notifications. Each filter has its own set of variables:

#### Links Filter <a id="filtr-ssylki"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.linkUrl` | [String](syntax/expressions.md#literals)​ | Detected link |
| `infraction.inviteCode` | [String](syntax/expressions.md#literals)​ | Detected invite code |
| `infraction.inviteUrl` | [String](syntax/expressions.md#literals)​ | Detected invite link `discord.gg/<code>` |

#### Bad Words Filter <a id="filtr-plokhie-slova"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.word` | [String](syntax/expressions.md#literals)​ | Detected bad word |

#### Repeated Text Filter <a id="filtr-povtoryaemyi-tekst"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.count` | [Number](syntax/expressions.md#literals)​ | Amount of messages triggered |

#### Caps Lock Filter <a id="filtr-caps-lock"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.percent` | [Number](syntax/expressions.md#literals)​ | Uppercase characters percent in the message |

#### Emotes Filter <a id="filtr-emocii"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.count` | [Number](syntax/expressions.md#literals)​ | Amount of emotes detected |

#### Mentions Filter <a id="filtr-upominaniya"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.mentionType` | [String](syntax/expressions.md#literals)​ | Type of detected excessive mentions |
| `infraction.count` | [Number](syntax/expressions.md#literals)​ | Amount of excessive mentions detected |

#### Zalgo Filter <a id="filtr-zalgo"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `infraction.percent` | [Number](syntax/expressions.md#literals)​ | Percentage of Zalgo-characters to the whole message |

### Custom Commands <a id="polzovatelskie-komandy"></a>

| Variable | Type | Description |
| :--- | :--- | :--- |
| `arguments` | ​[Arguments](types.md#arguments)​ | Information about arguments passed to the command. |

