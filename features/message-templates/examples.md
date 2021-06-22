---
description: Just some useful examples of the Message Template Engine features.
---

# Examples

## Random Values

### Random Number

Just a simple command using [random](advanced/functions.md#random) function that will print a random number from 0 to 100:

```c
You got: **{{ random(0, 100) }}**
```

### Random Text

Using the same [random](advanced/functions.md#random) function you can print a random text message:

```c
{{ random(['Hi!', 'Hello!', 'Its nice to meet you!']) }}
```

### Random Number using input range

Let's make it a bit more complicated. How about a custom command with random numbers based on member's input:

```cpp
{% require arguments.get(1) returning 'Please specify minimal value' %}
{% require arguments.get(2) returning 'Please specify maximal value' %}

{{ member }}, you got **{{ random(arguments.get(1), arguments.get(2)) }}**
```

This command checks if member entered first and second arguments as minimal and maximal values of random range and prints the result using those values.

### Random Number using input range with validation

The previous example has one drawback. If the user specifies non-numbers or the maximum value is less than the minimum, the [random](advanced/functions.md#random) function will return an error that doesn't look very clear to the member.

We need to make sure that the input has the valid numbers and that the maximum value is greater than the minimum. This can be done as follow:

```cpp
{% set minumum = arguments.get(1) %}
{% set maximum = arguments.get(2) %}

{% require minumum returning 'Please specify minimal value!' %}
{% require minumum is number returning 'Minimal value must be a number!' %}
{% require maximum returning 'Please specify maximal value!' %}
{% require maximum is number returning 'Maximal value must be a number!' %}

{% if (minumum > maximum) %}
  {% return 'Maximal value must be greater than minimal!' %}
{% endif %}

{{ member }}, you got **{{ random(minumum, maximum) }}**
```

### Random Picture

Okay and here is the BOSS FIGHT. Let's make our own command with random picture just like `!fox`, `!dog`, `!cat` with some fun message with member mention. Here is the `!pet` command:

```cpp
{% set targetMemberID = arguments.get(1) %}
{% set targetMemberMention = message.mentionedMembers[0] %}

{%- if (targetMemberMention) %} 
	{% set targetMember = targetMemberMention %}
{% elseif (targetMemberID) %}
	{% set targetMember = guild.getMember(targetMemberID) %}
{% else %}
	{% return 'Who needs pets?' %}
{% endif -%}

{% require targetMember returning 'Who needs pets?' %}

{% if (targetMember.id == member.id) %}
	{% return 'Petting yourself?' %}
{% endif %}

{%- global gif = random([
	'https://images-ext-1.discordapp.net/external/yOicyNxjyB_y1Cf3hCgsePnL36oofd1qjsyFRjDWOzc/https/cdn.weeb.sh/images/SyFmqkFwW.gif?width=432&height=243',
  'https://images-ext-2.discordapp.net/external/ab1ICw2oaiDaG8Y0DwlPClP7xG54Ie4kKcaFtn7Q8LU/https/cdn.weeb.sh/images/SktIxo20b.gif?width=486&height=273',
  'https://images-ext-2.discordapp.net/external/5ol3M2-FsEvm81oZXbS8rZdEdevG3qqDJ9faicEDrw8/https/cdn.weeb.sh/images/rJMskkFvb.gif?width=450&height=247',
  'https://images-ext-2.discordapp.net/external/jFzBryOm4sSnuGD1FDOhtzGW52leLqh6UmIR5l6meZw/https/cdn.weeb.sh/images/SJLaWWRSG.gif?width=486&height=274',
  'https://images-ext-1.discordapp.net/external/PzOpIvj5jAgz6bcEq7jwtXPbKgmSV-dVKSvPc__CsCQ/https/cdn.weeb.sh/images/rkl1xJYDZ.gif?width=486&height=304',
  'https://images-ext-2.discordapp.net/external/sSZt42u8v8sWfZ5pg1NNIhnR7eEzmDXRIm93_GZG6yU/https/cdn.weeb.sh/images/Hkccqp4A-.gif?width=450&height=350',
  'https://images-ext-2.discordapp.net/external/GN3TW6pXl-zupZ7Do5h4o1Pnm6ZA_2wj9RUqydghUW8/https/cdn.weeb.sh/images/Sk2FyQHpZ.gif?width=450&height=253',
  'https://images-ext-1.discordapp.net/external/8tlbO-PtNvDizaijNJSJrzY1-lGprkAw_aO95H196dQ/https/cdn.weeb.sh/images/r1Y5L6NCZ.gif?width=486&height=270',
  'https://images-ext-2.discordapp.net/external/Ml2iTnfjVuHGP-Lkz88WrGKJCv1cJ7UikuE2yvt3XgI/https/cdn.weeb.sh/images/rJWRykFvZ.gif?width=540&height=304',
  'https://images-ext-1.discordapp.net/external/mVv4CiNvJjVBP6PbQgzleqysb31wA-P3p7v02S8jpfc/https/cdn.weeb.sh/images/ryXj1JKDb.gif?width=432&height=243'
]) -%}

**{{ member.nickname }}** pets **{{ targetMember.nickname }}**! 
```

This commands expects a member mention or ID as input and will return an error if mention was not specified. It will also check if you want to pet yourself and will return a message about it.

The [random](advanced/functions.md#random) function is used to pick a random gif from the list. Note that we used a [global](advanced/tags.md#global) tag so we could use that variable in other Message Template field.

**In this case, we need to add an image so we will switch Message Template to Embed mode and paste this global variable into Embed's "Image Url" field:**

```cpp
{{ gif }}
```

## Other

### Member Attributes Example

It is possible to create a command that will increment a simple counter created as `used` member's attribute and will print its value:

```cpp
{{ member.getAttribute('used').increment(1) }}
```

We can also create a command that will store some word in the attribute named `words`.

```cpp
{% do member.getAttribute('words').update('Hello World!') %}
```

And later we will print it using another command, for example:

```cpp
{{ member.getAttribute('words').value }}
```

The previous example will send a "Hello World!" message if member used the first command before to store the `words` value. Bot will not send message if attribute is empty.

We can also print this value in the more natural way:

```cpp
{{ member.attributes.words.value }}
```

{% hint style="warning" %}
Keep in mind that you can only use up to 5 attributes in Message Template.
{% endhint %}

### Embed Message Example

```cpp
{% do channel
    .createEmbed()
    .withContent('Content outside the embed')
    .withTitle('Title', 'https://juniper.bot')
    .withDescription('Oh, hi!')
    .appendDescription('\nHow are you?')
    .withDate(1587713425964)
    .withColor('ffff00')
    .withThumbnail(member.avatarUrl)
    .withImage('https://i.pinimg.com/originals/a4/41/6e/a4416e024d691af3a2971e4114a6da7f.png')
    .withAuthor(member.nickname)
    .withFooter('Huff, bye!', member.avatarUrl)
    .addField('First field', 'Ah! A value of the first field', true)
    .addField('Second field', 'Something here too', true)
    .send()
%}
```

### Adding Role to Yourself

It is possible to create a custom command that will add a role to the member and will print something, for example:

```cpp
{{ member }}, enjoy playing Destiny?
{% if (member.addRole(390472433003659264)) -%}
  You got a The Guardian role!
{% else -%}
  You already have The Guardian role!
{% endif %}
```

This command will print a message depending on the fact if the role was given or not. This example uses `addRole` method of [Member](advanced/types.md#member) which accepts an ID of role.

{% hint style="warning" %}
Note that you can update member roles only once in Message Template.
{% endhint %}

### Adding Role to Mentioned Member

We can also add a role to mentioned member as follows:

```cpp
{% set targetMember = message.mentionedMembers[0] %}
{% require targetMember returning 'Please specify a member to give The Guardian role!' %}

{% if (targetMember.addRole(390472433003659264)) -%}
  {{ targetMember }}, moderator {{member}} gave you The Guardian role!
{% else -%}
  This member already have The Guardian role!
{% endif %}
```

This example differs from the previous one. The role is given to the member mentioned with the command, not to the one who invoked it.

{% hint style="warning" %}
Note that you can update member roles only once in Message Template.
{% endhint %}

### Ranking Role Rewards

Ranking level up announcement messages have a variables to print added and/or removed roles, let's print them:

```cpp
{{ member }}, you reached a new level: **{{ member.rank.level }}**!
{% if (not empty(rolesAdded)) -%}
You've got new roles: {{ join(rolesAdded) }}
{%- endif -%}
{% if (not empty(rolesRemoved)) %}
You've lost roles: {{ join(rolesRemoved) }}
{% endif %}
```

This template prints added and removed roles only if there was something to add and remove at this level.

It is better to use this template in Embed Content Template so you will not ping the members that have those roles.

### Report Command

It is possible to create a simple report command as follows:

1. Create a new text channel available only to bot and moderators;
2. Create a new custom command;
3. In custom command select the channel you created previously as target channel and switch to Embed mode;
4. Insert following to Embed Content Template:

```cpp
{% set targetMemberID = arguments.get(1) %}
{% set targetMemberMention = message.mentionedMembers[0] %}

{%- if (targetMemberMention) %} 
	{% global targetMember = targetMemberMention %}
{% elseif (targetMemberID) %}
	{% global targetMember = guild.getMember(targetMemberID) %}
{% endif -%}

{% global reason = arguments.after(2) %}

{% require targetMember and reason returning 'Please specify an ID or mention of member and the report description' %}

A [report]({{ message.jumpUrl }}) was created for {{ targetMember }}:

{{ reason }}

{% do sourceChannel.sendMessage(format('%s, your report was sent! Thank you.', member)) %}
```

This command requires a violators ID or mention and the report description that will be sent to moderators. 

The message template itself is sent to the created report channel so it responds to the command that the report was successfully sent.

{% hint style="warning" %}
Note that you can use `sendMessage` function only two times in Message Template.
{% endhint %}

