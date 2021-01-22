---
description: Примеры команд с использованием возможностей шаблонного движка JuniperBot.
---

# Полезные примеры

## Случайные значения

### Случайное число

Простая команда, которая, используя функцию [random](advanced/functions.md#random), выведет случайное число от 0 до 100:

```c
Вам выпало: **{{ random(0, 100) }}**
```

### Случайный текст

Используя функцию [random](advanced/functions.md#random) можно вывести случайный текст:

```c
{{ random(['Привет!', 'Хаюшки!', 'Здравствуйте!']) }}
```

### Случайное число в диапазоне

Более сложная команда случайных чисел, которая позволит участнику вводить свои значения границ:

```cpp
{% require arguments.get(1) returning 'Пожалуйста, укажите минимальное значение' %}
{% require arguments.get(2) returning 'Пожалуйста, максимальное значение' %}

{{ member }}, Вам выпало **{{ random(arguments.get(1), arguments.get(2)) }}**
```

Данная команда проверяет, были ли введены первый и второй аргумент как минимальное и максимальное значение, после чего выводит случайное значение в указанном диапазоне.

### Случайное число в диапазоне с проверкой ошибок

Предыдущий пример имеет один недостаток. Если пользователь укажет не числа или максимальное значение меньше минимального, функция вернет ошибку, которая не очень понятно выглядит для участника. 

Нужно убедиться, что введены корректные числа и что максимальное значение больше минимального. Это можно сделать следующим образом:

```cpp
{% set minumum = arguments.get(1) %}
{% set maximum = arguments.get(2) %}

{% require minumum returning 'Пожалуйста, укажите минимальное значение!' %}
{% require minumum is number returning 'Минимальное значение должно быть числом!' %}
{% require maximum returning 'Пожалуйста, укажите максимальное значение!' %}
{% require maximum is number returning 'Максимальное значение должно быть числом!' %}

{% if (minumum > maximum) %}
  {% return 'Максимальное значение должно быть больше минимального!' %}
{% endif %}

{{ member }}, Вам выпало **{{ random(minumum, maximum) }}**
```

### Случайная картинка

Более сложный пример. Вы можете сделать свою команду со случайной картинкой на подобии встроенных `!лис`, `!пёс`, `!кот`. Вы даже можете совместить это с каким-либо действием. Например, команда `!погладить`:

```cpp
{% set targetMemberID = arguments.get(1) %}
{% set targetMemberMention = message.mentionedMembers[0] %}

{%- if (targetMemberMention) %} 
	{% set targetMember = targetMemberMention %}
{% elseif (targetMemberID) %}
	{% set targetMember = guild.getMember(targetMemberID) %}
{% else %}
	{% return 'Кого гладить?' %}
{% endif -%}

{% require targetMember returning 'Кого гладить?' %}

{% if (targetMember.id == member.id) %}
	{% return 'Нельзя гладить себя :c' %}
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

**{{ targetMember.nickname }}**, тебя погладил(а) **{{ member.nickname }}**
```

Данная команда ожидает указания либо id участника, либо упоминание, иначе возвращает понятную участникам ошибку об этом. Она так же не позволяет погладить самого себя и тоже возвращает ошибку.

Далее используется команда [random](advanced/functions.md#random) для выбора случайной ссылки с картинкой или анимацией из списка. Обратите внимание, что переменная самой картинкой объявляется тегом [global](advanced/tags.md#global), это означает, что эту переменную можно будет использовать в других полях шаблона.

**Конкретно в данном случае, нам необходимо отобразить эту картинку, поэтому нам нужно переключить режим сообщения в "Панель" и ввести эту переменную в поле панели "Ссылка на полноразмерную картинку":**

```cpp
{{ gif }}
```

## Прочее

### Пример отправки Embed

```cpp
{% do channel
    .createEmbed()
    .withContent('Содержимое вне панели')
    .withTitle('Заголовок', 'https://juniper.bot')
    .withDescription('О! Привет!')
    .appendDescription('\nКак дела?')
    .withDate(1587713425964)
    .withColor('ffff00')
    .withThumbnail(member.avatarUrl)
    .withImage('https://i.pinimg.com/originals/a4/41/6e/a4416e024d691af3a2971e4114a6da7f.png')
    .withAuthor(member.nickname)
    .withFooter('Уф, пока!', member.avatarUrl)
    .addField('Первое поле', 'О, значение первого поля', true)
    .addField('Второе поле', 'Ну и здесь что-нибудь', true)
    .send()
%}
```

### Выдача себе роли с сообщением

Можно создать пользовательскую команду, которая вместе с произвольным сообщением выдаст какую-либо роль. Например:

```cpp
{{ member }}, любишь поиграть в Destiny?
{% if (member.addRole(390472433003659264)) -%}
  Тебе выдана роль стража!
{% else -%}
  Как я сама могла не догадаться, у тебя же роль стража!
{% endif %}
```

Данная команда выводит сообщение и дополняет его в зависимости от того, была ли выдана роль или нет. Здесь используется функция `addRole` у типа [Member](advanced/types.md#member), которая принимает аргументом id роли для выдачи.

{% hint style="warning" %}
Помните, что функции выдачи роли можно использовать только один раз в сообщении.
{% endhint %}

### Выдача роли с сообщением упомянутому участнику

Можно так же выдавать роль упомянутому участнику, например:

```cpp
{% set targetMember = message.mentionedMembers[0] %}
{% require targetMember returning 'Укажите участника, которому нужно выдать роль Стража!' %}

{% if (targetMember.addRole(390472433003659264)) -%}
  {{ targetMember }}, модератор {{member}} выдал вам роль Стража!
{% else -%}
  У этого участника уже есть роль Стража!
{% endif %}
```

Этот пример отличается от предыдущего тем, что роль выдается упомянутому вместе с командой участнику, а не тому, кто её вызвал.

{% hint style="warning" %}
Помните, что функции выдачи роли можно использовать только один раз в сообщении.
{% endhint %}

### Выдаваемые роли в сообщении повышения уровня

В сообщении о повышении уровня участника вы можете писать какие роли выдались и снялись, например:

```cpp
{{ member }}, ты получил новый уровень: **{{ member.rank.level }}**!
{% if (not empty(rolesAdded)) -%}
Тебе добавлены роли: {{ join(rolesAdded) }}
{%- endif -%}
{% if (not empty(rolesRemoved)) %}
С тебя сняты старые роли: {{ join(rolesRemoved) }}
{% endif %}
```

Сообщение показывает добавленные и снятые роли только если было что добавлять и снимать на этом уровне. 

Лучше вводить это в шаблон панели, поскольку будет выведен список упоминаний выданных и снятых ролей. Упоминания в панели срабатывать не будут, а роли будут красиво окрашиваться в их цвета.

### Команда репорта

Например, вы хотите сделать на сервере репорты. Сделайте следующее:

1. Создайте отдельный канал для репортов, доступный только модераторам и боту;
2. Создайте новую пользовательскую команду;
3. В пользовательской команде укажите канал репортов как целевой, включите режим панели;
4. В шаблон панели введите следующее:

```cpp
{% set targetMemberID = arguments.get(1) %}
{% set targetMemberMention = message.mentionedMembers[0] %}

{%- if (targetMemberMention) %} 
	{% global targetMember = targetMemberMention %}
{% elseif (targetMemberID) %}
	{% global targetMember = guild.getMember(targetMemberID) %}
{% endif -%}

{% global reason = arguments.after(2) %}

{% require targetMember and reason returning 'Пожалуйста, укажите ID или упоминание нарушителя и причину' %}

Был отправлен [репорт]({{ message.jumpUrl }}) на пользователя {{ targetMember }}:

{{ reason }}

{% do sourceChannel.sendMessage(format('%s, Ваш репорт успешно отправлен!', member)) %}
```

Данная команда требует указания id или упоминания нарушителя и причину репорта, которую необходимо передать модераторам. 

Сам шаблон сообщения отправляется в созданный канал репортов, одновременно с этим команда отвечает участнику в канале ввода команды, что репорт был успешно отправлен.

{% hint style="warning" %}
Помните, что функцию отправки сообщения `sendMessage` можно использовать только два раза за сообщение.
{% endhint %}

