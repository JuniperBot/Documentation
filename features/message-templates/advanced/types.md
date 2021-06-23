---
description: Data Types used in Template Engine
---

# Data Types

This article describes all the data types used in the JuniperBot Template Engine.

The most primitive data types \(strings, numbers, lists, maps\) are described in the [Expressions](syntax/expressions.md) section of the template engine manual.

Some methods in the tables below may have a invoke quota. Quota means how many times this method can be invoked per template. Attempts to invoke that exceed the specified quota will be ignored and will not take any action.

### Guild <a id="guild"></a>

This data type describes all available data about the server.

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `name` | [String](syntax/expressions.md#literals)​ | Name |
| `iconUrl` | ​[String](syntax/expressions.md#literals)​ | Icon URL |
| `afkTimeout` | [Number](syntax/expressions.md#literals)​ | AFK timeout for voice channels \(in minutes\) |
| `afkChannel` | ​[VoiceChannel](types.md#voicechannel)​ | AFK Voice Channel |
| `memberCount` | ​[Number](syntax/expressions.md#literals)​ | Amount of Members |
| `createdAt` | [Date​](functions.md#date) | Creation date and time |
| `owner` | [Member](types.md#member)​ | Owner |
| `selfMember` | ​[Member](types.md#member)​ | Bot's member instance |
| `boostCount` | [Number](syntax/expressions.md#literals)​ | Amount of active boosts |

#### Methods <a id="funkcii"></a>

| Method | Parameters | Returns | Description |
| :--- | :--- | :--- | :--- |
| `getTextChannel(ID)` | [Number](syntax/expressions.md#literals), [String](syntax/expressions.md#literals)​ | [TextChannel](types.md#textchannel)​ | Returns text channel by given id |
| `getVoiceChannel(ID)` | [Number](syntax/expressions.md#literals), [String](syntax/expressions.md#literals)​ | [VoiceChannel](types.md#voicechannel)​ | Returns voice channel by given id |
| `getMember(ID)` | [Number](syntax/expressions.md#literals), [String](syntax/expressions.md#literals)​ | [Member](types.md#member)​ | Returns member by given id |
| `getRole(ID)` | [Number](syntax/expressions.md#literals), [String](syntax/expressions.md#literals)​ | [Role](types.md#role)​ | Returns role by given id |

### Member <a id="member"></a>

This data type describes all available data about the member and operations over them.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `mention` | [String](syntax/expressions.md#literals)​ | Mention string |
| `nickname` | [String](syntax/expressions.md#literals)​ | Nickname on the server or original name |
| `tag` | [String](syntax/expressions.md#literals)​ | Full tag in the format `Nickname#1234` |
| `name` | [String](syntax/expressions.md#literals)​ | Name |
| `bot` | ​[Boolean](syntax/expressions.md#literals)​ | True if this member instance is bot |
| `discriminator` | [String](syntax/expressions.md#literals)​ | Descriminator \(4 digits after \#\) |
| `joinedAt` | [Date​](functions.md#date)​ | Join date and time |
| `createdAt` | [Date​](functions.md#date)​ | Registration date and time |
| `status` | [String](syntax/expressions.md#literals)​ | Status \(Online, Idle, DnD, Offline\) with emoji icon |
| `avatarUrl` | [String](syntax/expressions.md#literals)​ | Avatar URL |
| `bio` | [String](syntax/expressions.md#literals)​ | Bio specified in `!bio` |
| `rank` | ​[Rank​](types.md#rank) | Ranking data |
| `roles` | [List](syntax/expressions.md#lists)&lt;[Role](types.md#role)&gt; | List of assigned roles |
| `guild` | [Guild](types.md#guild)​ | Server information |
| `attributes` | [​AttributesStorage](types.md#attributesstorage)​ | Attributes storage |

#### Methods <a id="funkcii"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Returns</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Quota</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>hasRole(Role)</code>
      </td>
      <td style="text-align:left">
        <p><a href="syntax/expressions.md#literals">Number</a> (ID)</p>
        <p><a href="types.md#role">Role</a>&#x200B;</p>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Checks if member has this role</td>
        <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasPermission(Name)</code>
      </td>
      <td style="text-align:left">&#x200B;<a href="types.md#permission">Permission&#x200B;</a>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Checks if member has this permission over all his roles</td>
        <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasPermission(<br />  Channel, <br />  Name<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>
            <p>Channel:</p>
            <p><a href="syntax/expressions.md#literals">Number</a> (ID)
              <br /><a href="types.md#textchannel">TextChannel</a>&#x200B;</p>
          </li>
          <li>
            <p>Name:</p>
            <p>&#x200B;<a href="types.md#permission">Permission&#x200B;</a>&#x200B;</p>
          </li>
        </ul>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Checks if member has this permission in the channel specified</td>
        <td
        style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addRole(Role)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">Number</a> (ID)
        <br /><a href="types.md#role">Role</a>&#x200B;</td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Adds role to the member. Returns <code>true</code> if member roles were
        updated.</td>
        <td style="text-align:left">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addRoles(Roles)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#lists">List</a>&lt;<a href="syntax/expressions.md#literals">Number</a>(ID)&gt;</td>
      <td
      style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
        <td
        style="text-align:left">Adds roles to the member. Returns <code>true</code> if member roles were
          updated.</td>
          <td style="text-align:left">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>removeRole(Role)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">Number</a> (ID)
        <br /><a href="types.md#role">Role</a>&#x200B;</td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Removes role from the member. Returns <code>true</code> if member roles
        were updated.</td>
        <td style="text-align:left">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>removeRoles(Roles)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#lists">List</a>&lt;<a href="syntax/expressions.md#literals">Number</a>(ID)&gt;</td>
      <td
      style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
        <td
        style="text-align:left">Removes roles from the member. Returns <code>true</code> if member roles
          were updated.</td>
          <td style="text-align:left">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>modifyRoles(<br />  [Add], <br />  [Remove]<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Add:
            <br /><a href="syntax/expressions.md#lists">List</a>&lt;<a href="syntax/expressions.md#literals">Number</a>(ID)&gt;</li>
          <li>Remove:
            <br /><a href="syntax/expressions.md#lists">List</a>&lt;<a href="syntax/expressions.md#literals">Number</a>(ID)&gt;</li>
        </ul>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Adds and removes roles from the member atomatically. Returns <code>true</code> if
        member roles were updated.</td>
        <td style="text-align:left">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>modifyNickname(Name)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">
        <p>Changes member&apos;s nickname. Nickname length must be in range <code>[2, 32]</code>.</p>
        <p>Returns <code>true</code> if name was updated.</p>
        </td>
        <td style="text-align:left">1</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getAttribute(Key)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left">&#x200B;<a href="https://app.gitbook.com/@juniperbot/s/juniperbot/features/message-templates/advanced/types#attribute">Attribute</a>&#x200B;</td>
      <td
      style="text-align:left">Returns member attribute (stored value)</td>
        <td style="text-align:left">5</td>
    </tr>
  </tbody>
</table>

\* Role update methods have shared quota counter.‌

### Rank <a id="rank"></a>

This data type describes all available data about the member's rank and operations over them.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `level` | [Number](syntax/expressions.md#literals)​ | Member level |
| `remainingExp` | [Number](syntax/expressions.md#literals)​ | Remaining EXP until next level |
| `levelExp` | [Number](syntax/expressions.md#literals)​ | Total EXP required for current level |
| `levelCurrentExp` | [Number](syntax/expressions.md#literals)​ | Member's EXP on current level |
| `totalExp` | [Number](syntax/expressions.md#literals)​ | Total EXP member earned |
| `rank` | [Number](syntax/expressions.md#literals)​ | Member's rank position |
| `cookies` | [Number](syntax/expressions.md#literals)​ | Amount of cookies member have |
| `voiceActivity` | [String](syntax/expressions.md#literals)​ | Voice Activity duration formatted in text |
| `voiceActivityMs` | [Number](syntax/expressions.md#literals)​ | Voice Activity duration in milliseconds |

### TextChannel <a id="textchannel"></a>

This data type describes all available data about the text channel.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `name` | [String](syntax/expressions.md#literals)​ | Name |
| `mention` | [String](syntax/expressions.md#literals)​ | Mention |
| `topic` | [String](syntax/expressions.md#literals)​ | Description \(Topic\) |
| `position` | [Number](syntax/expressions.md#literals)​ | Position number in channel list \(1 is top of the list\) |
| `createdAt` | [Date​](functions.md#date)​ | Creation date and time |
| `guild` | [Guild](types.md#guild)​ | Server information |
| `parent` | ​[Category](types.md#category)​ | Category if exists |
| `canTalk` | ​[Boolean](syntax/expressions.md#literals)​ | `true` if bot can send messages in this channel |

#### Methods <a id="funkcii"></a>

| Method | Parameters | Returns | Description | Quota |
| :--- | :--- | :--- | :--- | :--- |
| `sendMessage(Text)` | [String](syntax/expressions.md#literals)​ | ​[Boolean](syntax/expressions.md#literals)​ | Sends a simple text message to this channel. Returns `true` if message were sent. | 1\* |
| `createEmbed()` | - | [​Embed](types.md#embed)​ | Creates a new Embed builder. | - |

\* Message send methods have shared quota counter.‌

### VoiceChannel <a id="voicechannel"></a>

This data type describes all available data about the voice channel.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `name` | [String](syntax/expressions.md#literals)​ | Name |
| `userLimit` | [Number](syntax/expressions.md#literals)​ | Member limit on the channel. 0 is no limit. |
| `bitrate` | [Number](syntax/expressions.md#literals)​ | Audio Bitrate |
| `position` | [Number](syntax/expressions.md#literals)​ | Position number in channel list \(1 is top of the list\) |
| `createdAt` | [Date​](functions.md#date)​ | Creation date and time |
| `parent` | ​[Category](types.md#category)​ | Category if exists |
| `guild` | [Guild](types.md#guild)​ | Server information |

### Category <a id="category"></a>

This data type describes all available data about the channel category.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `name` | [String](syntax/expressions.md#literals)​ | Name |
| `position` | [Number](syntax/expressions.md#literals)​ | Position number in channel list \(1 is top of the list\) |
| `createdAt` | [Date​](functions.md#date)​ | Creation date and time |
| `guild` | [Guild](types.md#guild)​ | Server information |

### Role <a id="role"></a>

This data type describes all available data about the role.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `name` | [String](syntax/expressions.md#literals)​ | Name |
| `position` | [Number](syntax/expressions.md#literals)​ | Position number in role list |
| `createdAt` | [Date​](functions.md#date)​ | Creation date and time |
| `permissionsRaw` | [Number](syntax/expressions.md#literals)​ | Permissions in raw numeric representation |
| `managed` | ​[Boolean](syntax/expressions.md#literals)​ | `true` if this role is managed by some integration |
| `hoisted` | ​[Boolean](syntax/expressions.md#literals)​ | `true` if this role is displayed separately from online members |
| `publicRole` | ​[Boolean](syntax/expressions.md#literals)​ | `true` if this is public role \(`@everyone`\) |
| `color` | [String](syntax/expressions.md#literals)​ | Color in `#RRGGBB` format |
| `guild` | [Guild](types.md#guild)​ | Server information |

#### Methods <a id="funkcii"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Returns</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>hasPermission(Name)</code>
      </td>
      <td style="text-align:left">&#x200B;<a href="types.md#permission">Permission&#x200B;</a>&#x200B;</td>
      <td
      style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
        <td
        style="text-align:left">Checks if this role has global permission</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasPermission(<br />  Channel, <br />  Name<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>
            <p>Channel:</p>
            <p>ID, <a href="types.md#textchannel">TextChannel</a>&#x200B;</p>
          </li>
          <li>
            <p>Name:</p>
            <p>&#x200B;<a href="types.md#permission">Permission&#x200B;</a>&#x200B;</p>
          </li>
        </ul>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Checks if this role has permission in channel specified</td>
    </tr>
  </tbody>
</table>

### Message <a id="message"></a>

This data type describes all available data about the message in text channel.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `contentRaw` | [String](syntax/expressions.md#literals)​ | The raw textual content of this message. |
| `contentDisplay` | [String](syntax/expressions.md#literals)​ | The textual content of this message in the format that would be shown to the Discord client. |
| `contentStripped` | [String](syntax/expressions.md#literals)​ | The textual content of this message in the format that would be shown to the Discord client and all the markdown stripped. |
| `jumpUrl` | [String](syntax/expressions.md#literals)​ | Jump-to URL |
| `channel` | [TextChannel](types.md#textchannel)​ | Channel of this message |
| `guild` | [Guild](types.md#guild)​ | Server information |
| `author` | [Member](types.md#member)​ | Message author |
| `createdAt` | [Date​](functions.md#date)​ | Creation date and time |
| `mentionedMembers` | [List](syntax/expressions.md#lists)&lt;[Member](types.md#member)&gt; | List of mentioned members |
| `mentionedChannels` | [List](syntax/expressions.md#lists)&lt;[TextChannel](types.md#textchannel)&gt; | List of mentioned text channels |
| `mentionedRoles` | [List](syntax/expressions.md#lists)&lt;[Role](types.md#role)&gt; | List of mentioned roles |
| `attachments` | [List](syntax/expressions.md#lists)&lt;[Attachment](types.md#attachment)&gt; | List of attachments |

### Attachment <a id="attachment"></a>

This data type describes all available data about the message attachment \(video, pictures, files\).‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `id` | [Number](syntax/expressions.md#literals)​ | Unique identifier |
| `createdAt` | [Date​](functions.md#date)​ | Creation date and time |
| `url` | [String](syntax/expressions.md#literals)​ | URL |
| `proxyUrl` | [String](syntax/expressions.md#literals)​ | Proxy URL |
| `fileName` | [String](syntax/expressions.md#literals)​ | File name |
| `size` | [Number](syntax/expressions.md#literals)​ | File size \(bytes\) |
| `height` | [Number](syntax/expressions.md#literals)​ | Image/Video height. `-1` for other file types |
| `width` | [Number](syntax/expressions.md#literals)​ | Image/Video width. `-1` for other file types |

### Embed <a id="embed"></a>

This data type describes the Embed message builder.‌ All the methods returns the same builder it is possible to build a method chains like this:

`withTitle('Title').withDescription('Description')`‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `empty` | ​[Boolean](syntax/expressions.md#literals)​ | `true` if empty |
| `validLength` | ​[Boolean](syntax/expressions.md#literals)​ | `true`if length is valid to sent this message |
| `length` | [Number](syntax/expressions.md#literals)​ | Current embed length |

#### Methods <a id="funkcii"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Returns</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Quota</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>withContent(Content)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets the message content outside the Embed</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withTitle(<br />  Name, <br />  URL<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Name:
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
          <li>URL (optional):
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets the Embed Title with URL</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withAuthor(<br />  Name, <br />  URL, <br />  IconURL<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Name:
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
          <li>URL (optional): <a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
          <li>IconURL (optional):
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets the Embed Author with optional link and icon</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withDescription(Content)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets the Embed Description</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>appendDescription(Content)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Appends new text to existing Embed Description</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withThumbnail(URL)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets Embed Thumbnail</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withImage(URL)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets Embed Image</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withColor(Color)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">
        <p>Sets Embed border color, this method accepts HEX color string, for example <code>#FF0000</code> for
          red (you can remove the #).</p>
        <p>&#x200B;<a href="https://htmlcolorcodes.com/">https://htmlcolorcodes.com/</a>&#x200B;</p>
      </td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addField(<br />  Name,<br />  Value,<br />  IsInline<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Name:
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
          <li>Value:
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
          <li>IsInline:
            <br />&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</li>
        </ul>
      </td>
      <td style="text-align:left">&#x200B;<a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Adds new Embed Field with name, value and inline option specified</td>
      <td
      style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withFooter(<br />  Content, <br />  IconURL<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Content:
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
          <li>IconURL (optional):
            <br /><a href="syntax/expressions.md#literals">String</a>&#x200B;</li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets Embed Footer with optional icon</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addReaction(Emote)</code>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">String</a>&#x200B;</td>
      <td
      style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
        <td style="text-align:left">Adds a reaction to the resulting message of this embed. Works the same
          as <a href="functions.md#reaction">reaction</a> function.</td>
        <td style="text-align:left">&#x200B;-</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>addButton(</code>
        </p>
        <p><code>  Type,<br />  URL,<br />  Content,<br />  Emote<br />)</code>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Type:
            <br /><a href="syntax/expressions.md#literals">String</a>
          </li>
          <li>URL:
            <br /><a href="syntax/expressions.md#literals">String</a>
          </li>
          <li>Content:
            <br /><a href="syntax/expressions.md#literals">String</a>
          </li>
          <li>
            <p>Emote
              <br />(optional):</p>
            <p><a href="syntax/expressions.md#literals">String</a>
            </p>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>
      </td>
      <td style="text-align:left">Adds a button to the resulting message of this embed. Works the same as
        <a
        href="functions.md#button">button</a>function.</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withDate(Date)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">String</a>,
        <br /><a href="syntax/expressions.md#literals">Number</a>,
        <br /><a href="functions.md#date">Date&#x200B;</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">
        <p>Adds a date to Embed Footer. Can accept:</p>
        <ul>
          <li>Unix timestamp number;</li>
          <li>Formatted string: <code>yyyy-MM-dd&apos;T&apos;HH:mm:ss.SSSZ</code>
          </li>
          <li>Date object</li>
        </ul>
      </td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addBlankField(IsInline)</code>
      </td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
        <td style="text-align:left">Adds en empty Embed Field with inline option</td>
        <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>clearFields()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Clears all the Embed Fields added</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>clear()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Clears the whole Embed data</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>error()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Makes this Embed styled as error, sets its color to red with Error title</td>
      <td
      style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>deleteAfterSec(Seconds)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">Number</a>&#x200B;</td>
      <td style="text-align:left"><a href="types.md#embed">&#x200B;Embed</a>&#x200B;</td>
      <td style="text-align:left">Sets the seconds after which this Embed message will be deleted</td>
      <td
      style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>send()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">Sends this Embed to the channel where this builder were created. Returns <code>true</code> if
        Embed was sent successfully.</td>
        <td style="text-align:left">2*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>update(Id)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#literals">Number</a>&#x200B;</td>
      <td style="text-align:left">&#x200B;<a href="syntax/expressions.md#literals">Boolean</a>&#x200B;</td>
      <td
      style="text-align:left">
        <p>Updates message with Embed by the Message ID given. Returns <code>true</code>,
          if message was successfully updated.</p>
        <p>&#x200B;</p>
        <p><b>You can only edit bot&apos;s messages!</b>
        </p>
        </td>
        <td style="text-align:left">2*</td>
    </tr>
  </tbody>
</table>

\* Message send methods have shared quota counter.‌

### AttributesStorage <a id="attributesstorage"></a>

This is dynamic type properties of that are automatically generated based on member's [attributes](types.md#attribute).

You can only access 5 attributes in single message template.‌

### Attribute <a id="attribute"></a>

This data type describes all available data about the member attribute.‌ Attributes are used to store custom data tied to member.

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `value` | [String](syntax/expressions.md#literals), [Number](syntax/expressions.md#literals), ​[Boolean](syntax/expressions.md#literals)​ | Current value |
| `updatedAt` | [Date​](functions.md#date)​ | Update date and time |

#### Methods <a id="funkcii"></a>

| Method | Parameters | Returns | Description | Quota |
| :--- | :--- | :--- | :--- | :--- |
| `update(Value)` | [String](syntax/expressions.md#literals), [Number](syntax/expressions.md#literals),  [Boolean](syntax/expressions.md#literals)​ | [String](syntax/expressions.md#literals), [Number](syntax/expressions.md#literals), [Boolean](syntax/expressions.md#literals)​ | Updates the attribute value with string, number or boolean specified. Max string length is 2000 characters. Returns the same value. | 1\* |
| `increment(Number)` | [Number](syntax/expressions.md#literals)​ | [Number](syntax/expressions.md#literals)​ | Increments the attribute for specified amount and returns new value. The counting starts from 0 if current value wasn't a number. | 1\* |
| `decrement(Number)` | [Number](syntax/expressions.md#literals)​ | [Number](syntax/expressions.md#literals)​ | Decrements the attribute for specified amount and returns new value. The counting starts from 0 if current value wasn't a number. | 1\* |
| `clear()` | - | - | Clears attribute and deletes it from database. | 1 |

\* Attribute update methods have the shared quota counter in scope of attribute.‌

### Arguments <a id="arguments"></a>

This data type describes the custom command message arguments.‌

#### Properties <a id="svoistva-1"></a>

| Property | Type | Description |
| :--- | :--- | :--- |
| `value` | [String](syntax/expressions.md#literals)​ | Original message string of command invocation. |
| `args` | [List](syntax/expressions.md#lists)&lt;[String](syntax/expressions.md#literals)&gt; | List of the arguments extracted from the string and split by whitespace. |

#### Methods <a id="funkcii"></a>

| Method | Parameters | Returns | Description |
| :--- | :--- | :--- | :--- |
| `get(Position)` | [Number](syntax/expressions.md#literals)​ | [String](syntax/expressions.md#literals)​ | Returns argument by its position |
| `after(Position)` | [Number](syntax/expressions.md#literals)​ | [String](syntax/expressions.md#literals)​ | Returns all the arguments after position specified |
| `before(Position)` | [Number](syntax/expressions.md#literals)​ | [String](syntax/expressions.md#literals)​ | Returns all the arguments before position specified |
| `range(   Start,   End )` | [Number](syntax/expressions.md#literals)​ | [String](syntax/expressions.md#literals)​ | Returns arguments from specified range |

{% hint style="info" %}
Arguments position start at 1.
{% endhint %}

### Permission <a id="permission"></a>

This data type describes all the permission available on the Discord. Pass them as [Strings](syntax/expressions.md#literals) to the method where they are expected.

| Permission | Description |
| :--- | :--- |
| `CREATE_INSTANT_INVITE` | Create Instant Invite |
| `KICK_MEMBERS` | Kick Members |
| `BAN_MEMBERS` | Ban Members |
| `ADMINISTRATOR` | Administrator |
| `MANAGE_CHANNEL` | Manage Channels |
| `MANAGE_SERVER` | Manage Server |
| `MESSAGE_ADD_REACTION` | Add Reactions |
| `VIEW_AUDIT_LOGS` | View Audit Logs |
| `PRIORITY_SPEAKER` | Priority Speaker |
| `VIEW_GUILD_INSIGHTS` | View Server Insights |
| `VIEW_CHANNEL` | Read Text Channels & See Voice Channels |
| `MESSAGE_READ` | Read Messages |
| `MESSAGE_WRITE` | Send Messages |
| `MESSAGE_TTS` | Send TTS Messages |
| `MESSAGE_MANAGE` | Manage Messages |
| `MESSAGE_EMBED_LINKS` | Embed Links |
| `MESSAGE_ATTACH_FILES` | Attach Files |
| `MESSAGE_HISTORY` | Read History |
| `MESSAGE_MENTION_EVERYONE` | Mention Everyone |
| `MESSAGE_EXT_EMOJI` | Use External Emojis |
| `USE_SLASH_COMMANDS` | Use Slash Commands |
| `VOICE_STREAM` | Video |
| `VOICE_CONNECT` | Connect |
| `VOICE_SPEAK` | Speak |
| `VOICE_MUTE_OTHERS` | Mute Members |
| `VOICE_DEAF_OTHERS` | Deafen Members |
| `VOICE_MOVE_OTHERS` | Move Members |
| `VOICE_USE_VAD` | Use Voice Activity |
| `NICKNAME_CHANGE` | Change Nickname |
| `NICKNAME_MANAGE` | Manage Nicknames |
| `MANAGE_ROLES` | Manage Roles |
| `MANAGE_PERMISSIONS` | Manage Permissions |
| `MANAGE_WEBHOOKS` | Manage Webhooks |
| `MANAGE_EMOTES` | Manage Emojis |

