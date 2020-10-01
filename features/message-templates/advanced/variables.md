---
description: Краткая справка по настройке шаблонов сообщений JuniperBot
---

# Входные данные

### Общие переменные

Все шаблоны имеют несколько изначально определенных переменных:

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41F;&#x435;&#x440;&#x435;&#x43C;&#x435;&#x43D;&#x43D;&#x430;&#x44F;</th>
      <th
      style="text-align:left">&#x422;&#x438;&#x43F;</th>
        <th style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>guild</code>
      </td>
      <td style="text-align:left"><a href="types.md#guild">Guild</a>
      </td>
      <td style="text-align:left">&#x414;&#x430;&#x43D;&#x43D;&#x44B;&#x435; &#x43E; &#x441;&#x435;&#x440;&#x432;&#x435;&#x440;&#x435;
        (&#x432;&#x44B;&#x432;&#x43E;&#x434;&#x438;&#x442; &#x43D;&#x430;&#x437;&#x432;&#x430;&#x43D;&#x438;&#x435;
        &#x43A;&#x430;&#x43D;&#x430;&#x43B;&#x430;)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>bot</code>
      </td>
      <td style="text-align:left"><a href="types.md#member">Member</a>
      </td>
      <td style="text-align:left">&#x42D;&#x43A;&#x437;&#x435;&#x43C;&#x43F;&#x43B;&#x44F;&#x440; JuniperBot
        &#x43A;&#x430;&#x43A; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;
        (&#x432;&#x44B;&#x432;&#x43E;&#x434;&#x438;&#x442; &#x443;&#x43F;&#x43E;&#x43C;&#x438;&#x43D;&#x430;&#x43D;&#x438;&#x435;)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>member</code>
      </td>
      <td style="text-align:left"><a href="types.md#member">Member</a>
      </td>
      <td style="text-align:left">&#x42D;&#x43A;&#x437;&#x435;&#x43C;&#x43F;&#x43B;&#x44F;&#x440; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;,
        &#x441;&#x432;&#x44F;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x433;&#x43E;
        &#x441; &#x448;&#x430;&#x431;&#x43B;&#x43E;&#x43D;&#x43E;&#x43C; (&#x432;&#x44B;&#x432;&#x43E;&#x434;&#x438;&#x442;
        &#x443;&#x43F;&#x43E;&#x43C;&#x438;&#x43D;&#x430;&#x43D;&#x438;&#x435;)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>channel</code>
      </td>
      <td style="text-align:left"><a href="types.md#textchannel">TextChannel</a>
      </td>
      <td style="text-align:left">&#x426;&#x435;&#x43B;&#x435;&#x432;&#x43E;&#x439; &#x43A;&#x430;&#x43D;&#x430;&#x43B;,
        &#x43A;&#x443;&#x434;&#x430; &#x434;&#x43E;&#x43B;&#x436;&#x43D;&#x43E;
        &#x431;&#x44B;&#x442;&#x44C; &#x43E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43B;&#x435;&#x43D;&#x43E;
        &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x435; (&#x442;&#x43E;&#x43B;&#x44C;&#x43A;&#x43E;
        &#x435;&#x441;&#x43B;&#x438; &#x43D;&#x430; &#x441;&#x430;&#x43C; &#x441;&#x435;&#x440;&#x432;&#x435;&#x440;,
        &#x430; &#x43D;&#x435; &#x432; &#x43B;&#x438;&#x447;&#x43A;&#x443;)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sourceChannel</code>
      </td>
      <td style="text-align:left"><a href="types.md#textchannel">TextChannel</a>
      </td>
      <td style="text-align:left">
        <p>&#x41A;&#x430;&#x43D;&#x430;&#x43B;-&#x438;&#x441;&#x442;&#x43E;&#x447;&#x43D;&#x438;&#x43A;
          (&#x43A;&#x430;&#x43D;&#x430;&#x43B; &#x432;&#x432;&#x43E;&#x434;&#x430;
          &#x43F;&#x43E;&#x43B;&#x44C;&#x437;&#x43E;&#x432;&#x430;&#x442;&#x435;&#x43B;&#x44C;&#x441;&#x43A;&#x43E;&#x439;
          &#x43A;&#x43E;&#x43C;&#x430;&#x43D;&#x434;&#x44B;, &#x43D;&#x430;&#x43F;&#x440;&#x438;&#x43C;&#x435;&#x440;).</p>
        <p>&#x41E;&#x442;&#x43B;&#x438;&#x447;&#x430;&#x435;&#x442;&#x441;&#x44F;
          &#x43E;&#x442; &#x43F;&#x435;&#x440;&#x435;&#x43C;&#x435;&#x43D;&#x43D;&#x43E;&#x439; <code>channel</code> &#x442;&#x435;&#x43C;,
          &#x432; &#x43F;&#x43E;&#x441;&#x43B;&#x435;&#x434;&#x43D;&#x435;&#x439;
          &#x43C;&#x43E;&#x436;&#x435;&#x442; &#x431;&#x44B;&#x442;&#x44C; &#x441;&#x43E;&#x432;&#x435;&#x440;&#x448;&#x435;&#x43D;&#x43D;&#x43E;
          &#x434;&#x440;&#x443;&#x433;&#x43E;&#x439; &#x43A;&#x430;&#x43D;&#x430;&#x43B;,
          &#x432;&#x44B;&#x431;&#x440;&#x430;&#x43D;&#x43D;&#x44B;&#x439; &#x432;&#x440;&#x443;&#x447;&#x43D;&#x443;&#x44E;
          &#x43A;&#x430;&#x43A; &#x446;&#x435;&#x43B;&#x435;&#x432;&#x43E;&#x439;
          &#x432; &#x43D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430;&#x445;
          &#x448;&#x430;&#x431;&#x43B;&#x43E;&#x43D;&#x430; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x44F;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>message</code>
      </td>
      <td style="text-align:left"><a href="types.md#message">Message</a>
      </td>
      <td style="text-align:left">
        <p>&#x42D;&#x43A;&#x437;&#x435;&#x43C;&#x43F;&#x43B;&#x44F;&#x440; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x44F;,
          &#x43A;&#x43E;&#x442;&#x43E;&#x440;&#x43E;&#x435; &#x43C;&#x43E;&#x433;&#x43B;&#x43E;
          &#x441;&#x43F;&#x440;&#x43E;&#x432;&#x43E;&#x446;&#x438;&#x440;&#x43E;&#x432;&#x430;&#x442;&#x44C;
          &#x43E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43A;&#x443; &#x433;&#x435;&#x43D;&#x435;&#x440;&#x430;&#x446;&#x438;&#x44E;
          &#x448;&#x430;&#x431;&#x43B;&#x43E;&#x43D;&#x430;.</p>
        <p>&#x41D;&#x430;&#x43F;&#x440;&#x438;&#x43C;&#x435;&#x440;, &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x435;
          &#x441; &#x432;&#x44B;&#x437;&#x43E;&#x432;&#x43E;&#x43C; &#x43F;&#x43E;&#x43B;&#x44C;&#x437;&#x43E;&#x432;&#x430;&#x442;&#x435;&#x43B;&#x44C;&#x441;&#x43A;&#x43E;&#x439;
          &#x43A;&#x43E;&#x43C;&#x430;&#x43D;&#x434;&#x44B;.</p>
      </td>
    </tr>
  </tbody>
</table>

Эти переменные всегда включаются во все шаблоны сообщений. Далее отдельно будут описываться только те места, где есть какие-либо дополнительные данные или требуются пояснения к переменным из общих данных.

### Рейтинг участников <a id="ranking"></a>

В дополнение к общим переменным выше, в рейтинг участников передаются следующие данные:

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `rolesAdded` | [Список](syntax/expressions.md#spiski)&lt;[Role](types.md#role)&gt; | Список выданных ролей-наград |
| `rolesRemoved` | [Список](syntax/expressions.md#spiski)&lt;[Role](types.md#role)&gt; | Список снятых ролей-наград |

### Автомодерация <a id="automod"></a>

Данные переменные используются в фильтрах автомодерации в уведомлениях о нарушении. Для каждого фильтра определен свой набор переменных, с которыми вы можете ознакомиться ниже.

#### Фильтр "Ссылки"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.linkUrl` | ​[Строка](syntax/expressions.md#primitivy) | Ссылка, попавшая под правила фильтра |
| `infraction.inviteCode` | ​[Строка](syntax/expressions.md#primitivy) | Код приглашения на сервер |
| `infraction.inviteUrl` | ​[Строка](syntax/expressions.md#primitivy) | Ссылка с приглашением на сервер в формате `discord.gg/<код>` |

#### Фильтр "Плохие слова"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.word` | ​[Строка](syntax/expressions.md#primitivy) | Обнаруженное плохое слово |

#### Фильтр "Повторяемый текст"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.count` | ​[Число](syntax/expressions.md#primitivy) | Количество одинаковых сообщений |

#### Фильтр "Caps Lock"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.percent` | ​[Число](syntax/expressions.md#primitivy) | Процент букв в верхнем регистре в сообщении |

#### Фильтр "Эмоции"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.count` | ​[Число](syntax/expressions.md#primitivy) | Количество обнаруженных эмоций в сообщении |

#### Фильтр "Упоминания"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.mentionType` | ​[Строка](syntax/expressions.md#primitivy) | Тип упоминаний, на которых сработал фильтр |
| `infraction.count` | ​[Число](syntax/expressions.md#primitivy) | Количество обнаруженных упоминаний этого типа |

#### Фильтр "Zalgo"

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `infraction.percent` | ​[Число](syntax/expressions.md#primitivy) | Процент Zalgo-символов от всего сообщения |

### Пользовательские команды

Дополнительные переменные для пользовательских команд.

| Переменная | Тип | Описание |
| :--- | :--- | :--- |
| `arguments` | [Arguments](types.md#arguments) | Данные об аргументах, вызвавших пользовательскую команду. |

