# Information

### help

This command is your best friend. Use it to get list of all available commands.

{% tabs %}
{% tab title="Usage" %}
```
!help [group]
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `хелп` |
| English | `help` |
{% endtab %}

{% tab title="Parameters" %}
| Parameter | Required | Type | Description |
| :--- | :---: | :--- | :--- |
| `group` | No | String | Name of the group |
{% endtab %}

{% tab title="Result" %}
Bot will respond \(to channel or DM\) with list of commands **available for this member** excluding those, to which member doesn't has access for some reasons.

For example, regular member will not see moderation commands or commands available only for specific set of roles.

If `group` parameter specified, it will respond with command list for this group with short descriptions.
{% endtab %}
{% endtabs %}

### info

Returns some useful information about bot.

{% tabs %}
{% tab title="Usage" %}
```
!info
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `инфо` |
| English | `info` |
{% endtab %}

{% tab title="Result" %}
Bot will respond with some useful information about it:

* Prefix;
* Developer name;
* Version and build date;
* Useful links;
* Platform information.
{% endtab %}
{% endtabs %}

### stats <a id="&#x441;&#x442;&#x430;&#x442;"></a>

Returns some bot's usage statistics.

{% tabs %}
{% tab title="Usage" %}
```
!stats
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `стат` |
| English | `stats` |
{% endtab %}

{% tab title="Result" %}
Bot will respond with some usage statistics:

* Servers count;
* Users and channels count;
* Platform uptime;
* Commands usage statistics.
{% endtab %}
{% endtabs %}

### serverinfo <a id="&#x441;&#x442;&#x430;&#x442;"></a>

Returns useful information about current server.

{% tabs %}
{% tab title="Usage" %}
```
!serverinfo
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `сервер` |
| English | `serverinfo` |
{% endtab %}

{% tab title="Result" %}
Bot will respond with some useful information about this server:

* Member count grouped by statuses;
* Channel count grouped by type;
* Verification level;
* Region;
* Owner;
* Creation date.
{% endtab %}
{% endtabs %}

### user

Returns some useful information about you or specified member.

{% tabs %}
{% tab title="Usage" %}
```
!user [@member]
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `юзер` |
| English | `user` |
{% endtab %}

{% tab title="Parameters" %}
| Parameter | Required | Type | Description |
| :--- | :---: | :--- | :--- |
| `@member` | No | Mention | Member you want to get information about |
{% endtab %}

{% tab title="Result" %}
Bot will respond with some useful information about you or `@mentioned` member:

* Member's own information specified by [bio ](information.md#bio)command;
* Member's name;
* Online status;
* Server joining date;
* Registration date;
* All information from [rank](ranking.md#rank) command for this member if ranking is enabled for this server.
{% endtab %}
{% endtabs %}

### bio

Use this command to show or set up your own information about yourself, which will be also available by [user](information.md#user) command.

{% tabs %}
{% tab title="Usage" %}
```
!bio [text]
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `осебе` |
| English | `bio` |
{% endtab %}

{% tab title="Parameters" %}
| Parameter | Required | Type | Description |
| :--- | :---: | :--- | :--- |
| `text` | No | String | Text you want to save in your profile |
{% endtab %}

{% tab title="Result" %}
* If `text` is specified, it will be saved in your profile;
* If minus sign \(`-`\) is specified as `text`, bio will be cleared;
* If `text` is not specified, bot will respond with your current bio.
{% endtab %}
{% endtabs %}

### inviteinfo

Returns some useful information about invite link.

{% tabs %}
{% tab title="Usage" %}
```
!inviteinfo <invite>
```
{% endtab %}

{% tab title="Aliases" %}
| Language | Alias |
| :--- | :--- |
| Russian | `инвайтинфо` |
| English | `inviteinfo` |
{% endtab %}

{% tab title="Parameters" %}
| Parameter | Required | Type | Description |
| :--- | :---: | :--- | :--- |
| `invite` | Yes | String | Invite link or code |
{% endtab %}

{% tab title="Result" %}
Bot will respond with some useful information about this invite link:

* Server's name and identifier;
* Channel's name and identifier;
* Name and identifier of user created this invite;
* Server's description \(if specified\);
* Server's verification level;
* If JuniperBot is on this server, additionally shows all available information from its [serverinfo](information.md#стат-1) command.
{% endtab %}
{% endtabs %}

