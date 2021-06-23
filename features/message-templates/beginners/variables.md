---
description: A Collection of the most used Message Template variables
---

# Variables

## Member <a id="member"></a>

A variables that prints some useful information about the member that invokec that command or event \(for example, level up announcement\).

| Variable | Description |
| :--- | :--- |
| `{{member}}` | Mention |
| `{{member.id}}` | Unique Identifier |
| `{{member.mention}}` | Mention |
| `{{member.nickname}}` | Nickname on the server or original name |
| `{{member.tag}}` | Full tag in the format `Nickname#1234` |
| `{{member.name}}` | Name |
| `{{member.discriminator}}` | Descriminator \(4 digits after \#\) |
| `{{member.joinedAt}}` | Join date and time |
| `{{member.createdAt}}` | Registration date and time |
| `{{member.status}}` | Status \(Online, Idle, DnD, Offline\) with emoji icon |
| `{{member.bio}}` | Bio specified in `!bio` |
| `{{member.avatarUrl}}` | Avatar URL |
| `{{member.rank.level}}` | Member level |
| `{{member.rank.remainingExp}}` | Remaining EXP until next level |
| `{{member.rank.levelExp}}` | Total EXP required for current level |
| `{{member.rank.levelCurrentExp}}` | Member's EXP on current level |
| `{{member.rank.totalExp}}` | Total EXP member earned |
| `{{member.rank.rank}}` | Member's rank position |
| `{{member.rank.cookies}}` | Amount of cookies member have |
| `{{member.rank.voiceActivity}}` | Voice Activity duration |

## Guild <a id="guild"></a>

A variables that prints some useful information about your server.

| Variable | Description |
| :--- | :--- |
| `{{guild}}` | Name |
| `{{guild.owner}}` | Owner mention |
| `{{guild.id}}` | Unique identifier |
| `{{guild.name}}` | Name |
| `{{guild.iconUrl}}` | Icon URL |
| `{{guild.afkTimeout}}` | AFK timeout for voice channels \(in minutes\) |
| `{{guild.afkChannel}}` | AFK Voice Channel |
| `{{guild.memberCount}}` | Amount of Members |
| `{{guild.createdAt}}` | Creation date and time |
| `{{guild.boostCount}}` | Amount of active boosts |

## Channel <a id="channel"></a>

A variables that prints some useful information about the target channel of message template \(will not work for DM messages\).

| Variable | Description |
| :--- | :--- |
| `{{channel}}` | Mention |
| `{{channel.id}}` | Unique identifier |
| `{{channel.name}}` | Name |
| `{{channel.mention}}` | Mention |
| `{{channel.topic}}` | Description \(Topic\) |
| `{{channel.position}}` | Position number in channel list \(1 is top of the list\) |
| `{{channel.createdAt}}` | Creation date and time |

## Message <a id="message"></a>

A variables that prints some useful information about the source message.

| Variable | Description |
| :--- | :--- |
| `{{message}}` | Message Content \(`{{message.contentRaw}}`\) |
| `{{message.id}}` | Unique identifier |
| `{{message.contentRaw}}` | The raw textual content of this message. |
| `{{message.contentDisplay}}` | The textual content of this message in the format that would be shown to the Discord client. |
| `{{message.contentStripped}}` | The textual content of this message in the format that would be shown to the Discord client and all the markdown stripped. |
| `{{message.author}}` | Message author |
| `{{message.createdAt}}` | Creation date and time |
| `{{message.mentionedMembers[0]}}` | The first mentioned member. Count starts from 0, enter 1 for second, etc. |
| `{{message.mentionedRoles}}` | List of mentioned roles |
| `{{message.mentionedRoles[0]}}` | The first mentioned role. Count starts from 0, enter 1 for second, etc. |
| `{{message.mentionedChannels}}` | List of mentioned text channels |
| `{{message.mentionedChannels[0]}}` | The first mentioned channel. Count starts from 0, enter 1 for second, etc. |
| `{{message.attachments}}` | List of attachments |
| `{{message.attachments[0]}}` | The first attachment. Count starts from 0, enter 1 for second, etc. |

## Member Ranking <a id="ranking"></a>

Additional Member Ranking variables.

| Variable | Description |
| :--- | :--- |
| `{{rolesAdded}}` | List of role-rewards added |
| `{{rolesRemoved}}` | List of role-rewards removed |

## Custom Commands <a id="custom-commands"></a>

Additional variables for custom commands.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Variable</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>{{arguments}}</code>
      </td>
      <td style="text-align:left">The text entered with the command. For example, for the command <code>!command Hello There!</code> arguments
        would be <code>Hello There!</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>{{arguments.get(N)}}</code>
      </td>
      <td style="text-align:left">
        <p>Get an argument entered with the command. Arguments split by whitespace
          so you should insert its position number as <code>N</code> :</p>
        <ul>
          <li><code>{{arguments.get(1)}}</code> for first argument;</li>
          <li><code>{{arguments.get(2)}}</code> for second, etc;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>{{arguments.range(N,M)}}</code>
      </td>
      <td style="text-align:left">Get a range of arguments. For example, <code>{{arguments.range(2,5)}}</code> will
        print arguments starting from second to fifth.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>{{arguments.after(2)}}</code>
      </td>
      <td style="text-align:left">Get all arguments starting from second. Pick your number.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>{{arguments.before(4)}}</code>
      </td>
      <td style="text-align:left">Get arguments starting from first to the fourth. Pick your number.</td>
    </tr>
  </tbody>
</table>

## Auto-Moderation <a id="automod"></a>

These variables are used in Auto-Moderation Filters for violation notifications. Each filter has its own set of variables:‌

#### Links Filter <a id="filtr-ssylki"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.linkUrl}}` | Detected link |
| `{{infraction.inviteCode}}` | Detected invite code |
| `{{infraction.inviteUrl}}` | Detected invite link `discord.gg/<code>` |

#### Bad Words Filter <a id="filtr-plokhie-slova"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.word}}` | Detected bad word |

#### Repeated Text Filter <a id="filtr-povtoryaemyi-tekst"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.count}}` | Amount of messages triggered |

#### Caps Lock Filter <a id="filtr-caps-lock"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.percent}}` | Uppercase characters percent in the message |

#### Emotes Filter <a id="filtr-emocii"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.count}}` | Amount of emotes detected |

#### Mentions Filter <a id="filtr-upominaniya"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.mentionType}}` | Type of detected excessive mentions |
| `{{infraction.count}}` | Amount of excessive mentions detected |

#### Zalgo Filter <a id="filtr-zalgo"></a>

| Variable | Description |
| :--- | :--- |
| `{{infraction.percent}}` | Percentage of Zalgo-characters to the whole message |

