---
description: 'Типы данных, используемые в шаблонном движке JuniperBot'
---

# Типы данных

В данной статье описываются все типы данных, используемые в шаблонном движке JuniperBot.

Самые примитивные типы данных \(строки, числа, списки, карты\) описаны в разделе [Выражения](syntax/expressions.md) руководства по шаблонному движку.

У некоторых методов в таблицах ниже может указываться квота вызовов. Квота означает сколько раз можно вызвать этот метод за шаблон. Вызовы, превышающие указанную квоту, будут проигнорированы и не будут выполнять никаких действий.

### Guild

Этот тип данных описывает все доступные данные о сервере.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор сервера |
| `name` | [Строка](syntax/expressions.md#primitivy) | Имя сервера |
| `iconUrl` | [Строка](syntax/expressions.md#primitivy) | Ссылка на иконку сервера |
| `afkTimeout` | [Число](syntax/expressions.md#primitivy) | AFK таймаут голосового канала \(в минутах\) |
| `afkChannel` | [VoiceChannel](types.md#voicechannel) | AFK голосовой канал |
| `memberCount` | [Число](syntax/expressions.md#primitivy) | Количество участников на сервере |
| `createdAt` | [Date](functions.md#date) | Дата и время создания сервера |
| `owner` | [Member](types.md#member) | Владелец сервера |
| `selfMember` | [Member](types.md#member) | Данные о самом боте на сервере |
| `boostCount` | [Число](syntax/expressions.md#primitivy) | Количество бустов на сервере |

#### Методы

| Метод | Параметры | Возвращает | Описание |
| :--- | :--- | :--- | :--- |
| `getTextChannel(ID)` | [Число](syntax/expressions.md#primitivy),  [Строка](syntax/expressions.md#primitivy) | [TextChannel](types.md#textchannel) | Возвращает текстовый канал сервера по его id |
| `getVoiceChannel(ID)` | [Число](syntax/expressions.md#primitivy),  [Строка](syntax/expressions.md#primitivy) | [VoiceChannel](types.md#voicechannel) | Возвращает голосовой канал сервера по его id |
| `getMember(ID)` | [Число](syntax/expressions.md#primitivy),  [Строка](syntax/expressions.md#primitivy) | [Member](types.md#member) | Возвращает участника сервера по его id |
| `getRole(ID)` | [Число](syntax/expressions.md#primitivy),  [Строка](syntax/expressions.md#primitivy) | [Role](types.md#role) | Возвращает роль сервера по его id |

### Member

Этот тип данных описывает все доступные данные об участнике сервера и операции над ним.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор участника |
| `mention` | [Строка](syntax/expressions.md#primitivy) | Упоминание участника |
| `nickname` | [Строка](syntax/expressions.md#primitivy) | Никнейм участника на сервере \(если установлен\) или его оригинальное  имя |
| `tag` | [Строка](syntax/expressions.md#primitivy) | Полный тэг участника в формате `Ник#1234` |
| `name` | [Строка](syntax/expressions.md#primitivy) | Имя участника |
| `bot` | [Логический](syntax/expressions.md#primitivy) | Признак, является ли указанный участник ботом |
| `discriminator` | [Строка](syntax/expressions.md#primitivy) | Дискриминатор участника \(4 числа после \#\) |
| `joinedAt` | [Date](functions.md#date) | Дата и время присоединения участника на сервер |
| `createdAt` | [Date](functions.md#date) | Дата и время регистрации участника |
| `status` | [Строка](syntax/expressions.md#primitivy) | Статус участника \(В сети, Нет на месте, Не беспокоить, Оффлайн\) с иконкой-эмоцией. |
| `avatarUrl` | [Строка](syntax/expressions.md#primitivy) | Ссылка на аватар участника |
| `bio` | [Строка](syntax/expressions.md#primitivy) | Информация об участнике, указанная в команде `!осебе` |
| `rank` | [Rank](types.md#rank) | Данные о рейтинге участника на сервере |
| `roles` | [Список](syntax/expressions.md#spiski)&lt;[Role](types.md#role)&gt; | Список ролей участника |
| `guild` | [Guild](types.md#guild) | Данные о сервере |
| `attributes` | [AttributesStorage](types.md#attributesstorage) | Атрибуты участника |

#### Методы

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41C;&#x435;&#x442;&#x43E;&#x434;</th>
      <th style="text-align:left">&#x41F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x44B;</th>
      <th
      style="text-align:left">&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;</th>
        <th
        style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
          <th style="text-align:center">&#x41A;&#x432;&#x43E;&#x442;&#x430;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>hasRole(&#x420;&#x43E;&#x43B;&#x44C;)</code>
      </td>
      <td style="text-align:left">
        <p><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a> (ID)</p>
        <p><a href="types.md#role">Role</a>
        </p>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41F;&#x440;&#x43E;&#x432;&#x435;&#x440;&#x44F;&#x435;&#x442;, &#x435;&#x441;&#x442;&#x44C;
        &#x43B;&#x438; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x430;&#x44F;
        &#x440;&#x43E;&#x43B;&#x44C; &#x443; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasPermission(&#x41D;&#x430;&#x437;&#x432;&#x430;&#x43D;&#x438;&#x435;)</code>
      </td>
      <td style="text-align:left"><a href="types.md#permission">Permission</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41F;&#x440;&#x43E;&#x432;&#x435;&#x440;&#x44F;&#x435;&#x442;, &#x435;&#x441;&#x442;&#x44C;
        &#x43B;&#x438; &#x443; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x435; &#x440;&#x430;&#x437;&#x440;&#x435;&#x448;&#x435;&#x43D;&#x438;&#x435;
        (&#x433;&#x43B;&#x43E;&#x431;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;)</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasPermission(<br />  &#x41A;&#x430;&#x43D;&#x430;&#x43B;, <br />  &#x41D;&#x430;&#x437;&#x432;&#x430;&#x43D;&#x438;&#x435;<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>
            <p>&#x41A;&#x430;&#x43D;&#x430;&#x43B;:</p>
            <p><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a> (ID)
              <br
              /><a href="types.md#textchannel">TextChannel</a>
            </p>
          </li>
          <li>
            <p>&#x41D;&#x430;&#x437;&#x432;&#x430;&#x43D;&#x438;&#x435;:</p>
            <p><a href="types.md#permission">Permission</a>
            </p>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41F;&#x440;&#x43E;&#x432;&#x435;&#x440;&#x44F;&#x435;&#x442;, &#x435;&#x441;&#x442;&#x44C;
        &#x43B;&#x438; &#x443; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x435; &#x440;&#x430;&#x437;&#x440;&#x435;&#x448;&#x435;&#x43D;&#x438;&#x435;
        &#x432; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x43C;
        &#x43A;&#x430;&#x43D;&#x430;&#x43B;&#x435;</td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addRole(&#x420;&#x43E;&#x43B;&#x44C;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a> (ID)
        <br
        /><a href="types.md#role">Role</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x412;&#x44B;&#x434;&#x430;&#x435;&#x442; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x443;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x443;&#x44E; &#x440;&#x43E;&#x43B;&#x44C;.
        &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
        &#x435;&#x441;&#x43B;&#x438; &#x43D;&#x430;&#x431;&#x43E;&#x440; &#x440;&#x43E;&#x43B;&#x435;&#x439;
        &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430; &#x431;&#x44B;&#x43B;
        &#x438;&#x437;&#x43C;&#x435;&#x43D;&#x451;&#x43D;.</td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addRoles(&#x420;&#x43E;&#x43B;&#x438;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x43F;&#x438;&#x441;&#x43E;&#x43A;</a>&lt;
        <a
        href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>(ID)&gt;</td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x412;&#x44B;&#x434;&#x430;&#x435;&#x442; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x443;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x435; &#x440;&#x43E;&#x43B;&#x438;.
        &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
        &#x435;&#x441;&#x43B;&#x438; &#x43D;&#x430;&#x431;&#x43E;&#x440; &#x440;&#x43E;&#x43B;&#x435;&#x439;
        &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430; &#x431;&#x44B;&#x43B;
        &#x438;&#x437;&#x43C;&#x435;&#x43D;&#x451;&#x43D;.</td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>removeRole(&#x420;&#x43E;&#x43B;&#x44C;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a> (ID)
        <br
        /><a href="types.md#role">Role</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x421;&#x43D;&#x438;&#x43C;&#x430;&#x435;&#x442; &#x441; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x443;&#x44E; &#x440;&#x43E;&#x43B;&#x44C;.
        &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
        &#x435;&#x441;&#x43B;&#x438; &#x43D;&#x430;&#x431;&#x43E;&#x440; &#x440;&#x43E;&#x43B;&#x435;&#x439;
        &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430; &#x431;&#x44B;&#x43B;
        &#x438;&#x437;&#x43C;&#x435;&#x43D;&#x451;&#x43D;.</td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>removeRoles(&#x420;&#x43E;&#x43B;&#x438;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x43F;&#x438;&#x441;&#x43E;&#x43A;</a>&lt;
        <a
        href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>(ID)&gt;</td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x421;&#x43D;&#x438;&#x43C;&#x430;&#x435;&#x442; &#x441; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x435; &#x440;&#x43E;&#x43B;&#x438;.
        &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
        &#x435;&#x441;&#x43B;&#x438; &#x43D;&#x430;&#x431;&#x43E;&#x440; &#x440;&#x43E;&#x43B;&#x435;&#x439;
        &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430; &#x431;&#x44B;&#x43B;
        &#x438;&#x437;&#x43C;&#x435;&#x43D;&#x451;&#x43D;.</td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>modifyRoles(<br />  [&#x414;&#x43E;&#x431;&#x430;&#x432;&#x438;&#x442;&#x44C;], <br />  [&#x421;&#x43D;&#x44F;&#x442;&#x44C;]<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>&#x414;&#x43E;&#x431;&#x430;&#x432;&#x438;&#x442;&#x44C;: <a href="syntax/expressions.md#primitivy">&#x421;&#x43F;&#x438;&#x441;&#x43E;&#x43A;</a>&lt;
            <a
            href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>(ID)&gt;</li>
          <li>&#x421;&#x43D;&#x44F;&#x442;&#x44C;:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x43F;&#x438;&#x441;&#x43E;&#x43A;</a>&lt;
            <a
            href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>(ID)&gt;</li>
        </ul>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x414;&#x43E;&#x431;&#x430;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x438;
        &#x441;&#x43D;&#x438;&#x43C;&#x430;&#x435;&#x442; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x435;
        &#x440;&#x43E;&#x43B;&#x438; &#x443; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;.
        &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
        &#x435;&#x441;&#x43B;&#x438; &#x43D;&#x430;&#x431;&#x43E;&#x440; &#x440;&#x43E;&#x43B;&#x435;&#x439;
        &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430; &#x431;&#x44B;&#x43B;
        &#x438;&#x437;&#x43C;&#x435;&#x43D;&#x451;&#x43D;.</td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>modifyNickname(&#x418;&#x43C;&#x44F;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">
        <p>&#x418;&#x437;&#x43C;&#x435;&#x43D;&#x44F;&#x435;&#x442; &#x43D;&#x438;&#x43A;&#x43D;&#x435;&#x439;&#x43C;
          &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x443;. &#x414;&#x43B;&#x438;&#x43D;&#x430;
          &#x43D;&#x438;&#x43A;&#x43D;&#x435;&#x439;&#x43C;&#x430; &#x434;&#x43E;&#x43B;&#x436;&#x43D;&#x430;
          &#x431;&#x44B;&#x442;&#x44C; &#x432; &#x434;&#x438;&#x430;&#x43F;&#x430;&#x437;&#x43E;&#x43D;&#x435;
          &#x43E;&#x442; 2 &#x434;&#x43E; 32 &#x441;&#x438;&#x43C;&#x432;&#x43E;&#x43B;&#x43E;&#x432;.</p>
        <p>&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
          &#x435;&#x441;&#x43B;&#x438; &#x438;&#x43C;&#x44F; &#x431;&#x44B;&#x43B;&#x43E;
          &#x443;&#x441;&#x43F;&#x435;&#x448;&#x43D;&#x43E; &#x438;&#x437;&#x43C;&#x435;&#x43D;&#x435;&#x43D;&#x43E;.</p>
      </td>
      <td style="text-align:center">1</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getAttribute(&#x41A;&#x43B;&#x44E;&#x447;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#attribute">Attribute</a>
      </td>
      <td style="text-align:left">&#x41F;&#x43E;&#x43B;&#x443;&#x447;&#x430;&#x435;&#x442; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x439;
        &#x430;&#x442;&#x440;&#x438;&#x431;&#x443;&#x442; &#x443;&#x447;&#x430;&#x441;&#x442;&#x43D;&#x438;&#x43A;&#x430;
        (&#x445;&#x440;&#x430;&#x43D;&#x438;&#x43C;&#x43E;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;)</td>
      <td
      style="text-align:center">5</td>
    </tr>
  </tbody>
</table>

\* У всех методов изменения ролей общий счётчик квоты вызовов.

### Rank <a id="rank"></a>

Этот тип данных описывает данные о рейтинге участника на сервере.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `level` | [Число](syntax/expressions.md#primitivy) | Уровень участника |
| `remainingExp` | [Число](syntax/expressions.md#primitivy) | Опыт, оставшийся до следующего уровня |
| `levelExp` | [Число](syntax/expressions.md#primitivy) | Суммарный опыт, необходимый на текущем уровне |
| `levelCurrentExp` | [Число](syntax/expressions.md#primitivy) | Опыт на текущем уровне |
| `totalExp` | [Число](syntax/expressions.md#primitivy) | Всего опыта у участника |
| `rank` | [Число](syntax/expressions.md#primitivy) | Ранг участника по серверу |
| `cookies` | [Число](syntax/expressions.md#primitivy) | Количество печенек участника |
| `voiceActivity` | [Строка](syntax/expressions.md#primitivy) | Длительность голосовой активности участника текстом |
| `voiceActivityMs` | [Число](syntax/expressions.md#primitivy) | Длительность голосовой активности участника в миллисекундах |

### TextChannel <a id="textchannel"></a>

Этот тип данных описывает все доступные данные о текстовом канале сервера.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор канала |
| `name` | [Строка](syntax/expressions.md#primitivy) | Название канала |
| `mention` | [Строка](syntax/expressions.md#primitivy) | Упоминание канала |
| `topic` | [Строка](syntax/expressions.md#primitivy) | Описание \(топик\) канала |
| `position` | [Число](syntax/expressions.md#primitivy) | Номер позиции канала в списке \(1 - верх списка\) |
| `createdAt` | [Date](functions.md#date) | Дата и время создание канала |
| `guild` | [Guild](types.md#guild) | Данные о сервере канала |
| `parent` | [Category](types.md#category) | Категория канала \(если есть\) |
| `canTalk` | [Логический](syntax/expressions.md#primitivy) | Признак, может ли бот отправлять сообщения в этот канал |

#### Методы

| Метод | Параметры | Возвращает | Описание | Квота |
| :--- | :--- | :--- | :--- | :---: |
| `sendMessage(Текст)` | [Строка](syntax/expressions.md#primitivy) | [Логический](syntax/expressions.md#primitivy) | Отправляет в этот канал указанный текст. Возвращает `true`, если сообщение было успешно отправлено. | 1\* |
| `createEmbed()` | - | [Embed](types.md#embed) | Создает новый конструктор панели \(Embed\) | - |

\* У всех методов отправки сообщений общий счётчик квоты вызовов.

### VoiceChannel

Этот тип данных описывает все доступные данные о голосовом канале сервера.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор канала |
| `name` | [Строка](syntax/expressions.md#primitivy) | Название канала |
| `userLimit` | [Число](syntax/expressions.md#primitivy) | Лимит участников в канале. `0` - без лимита. |
| `bitrate` | [Число](syntax/expressions.md#primitivy) | Битрейт аудио в канале |
| `position` | [Число](syntax/expressions.md#primitivy) | Номер позиции канала в списке \(1 - верх списка\) |
| `createdAt` | [Date](functions.md#date) | Дата и время создание канала |
| `parent` | [Category](types.md#category) | Категория канала \(если есть\) |
| `guild` | [Guild](types.md#guild) | Данные о сервере канала |

### Category

Этот тип данных описывает все доступные данные о категории \(группы\) каналов.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор категории |
| `name` | [Строка](syntax/expressions.md#primitivy) | Название категории |
| `position` | [Число](syntax/expressions.md#primitivy) | Номер позиции категории в списке \(1 - верх списка\) |
| `createdAt` | [Date](functions.md#date) | Дата и время создание категории |
| `guild` | [Guild](types.md#guild) | Данные о сервере категории |

### Role

Этот тип данных описывает все доступные данные о роли сервера.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор роли |
| `name` | [Строка](syntax/expressions.md#primitivy) | Название роли |
| `position` | [Число](syntax/expressions.md#primitivy) | Номер позиции роли |
| `createdAt` | [Date](https://docs.juniper.bot/features/message-templates/advanced/functions#date) | Дата и время создания роли |
| `permissionsRaw` | [Число](syntax/expressions.md#primitivy) | Числовое представление всех разрешений этой роли |
| `managed` | [Логический](syntax/expressions.md#primitivy) | Признак того, управляется ли эта роль интеграцией |
| `hoisted` | [Логический](syntax/expressions.md#primitivy) | Признак того, отображаются ли участники с этой ролью отдельно в списке участников |
| `publicRole` | [Логический](syntax/expressions.md#primitivy) | Признак того, является ли эта роль публичной ролью `@everyone` |
| `color` | [Строка](syntax/expressions.md#primitivy) | Цвет роли в формате `#RRGGBB` |
| `guild` | [Guild](types.md#guild) | Данные о сервере роли |

#### Методы

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41C;&#x435;&#x442;&#x43E;&#x434;</th>
      <th style="text-align:left">&#x41F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x44B;</th>
      <th
      style="text-align:left">&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;</th>
        <th
        style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>hasPermission(&#x41D;&#x430;&#x437;&#x432;&#x430;&#x43D;&#x438;&#x435;)</code>
      </td>
      <td style="text-align:left"><a href="types.md#permission">Permission</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41F;&#x440;&#x43E;&#x432;&#x435;&#x440;&#x44F;&#x435;&#x442;, &#x435;&#x441;&#x442;&#x44C;
        &#x43B;&#x438; &#x443; &#x440;&#x43E;&#x43B;&#x438; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x435;
        &#x440;&#x430;&#x437;&#x440;&#x435;&#x448;&#x435;&#x43D;&#x438;&#x435;
        (&#x433;&#x43B;&#x43E;&#x431;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasPermission(<br />  &#x41A;&#x430;&#x43D;&#x430;&#x43B;, <br />  &#x420;&#x430;&#x437;&#x440;&#x435;&#x448;&#x435;&#x43D;&#x438;&#x435;<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>
            <p>&#x41A;&#x430;&#x43D;&#x430;&#x43B;:</p>
            <p>ID,<a href="types.md#textchannel"> TextChannel</a>
            </p>
          </li>
          <li>
            <p>&#x420;&#x430;&#x437;&#x440;&#x435;&#x448;&#x435;&#x43D;&#x438;&#x435;:</p>
            <p><a href="types.md#permission">Permission</a>
            </p>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41F;&#x440;&#x43E;&#x432;&#x435;&#x440;&#x44F;&#x435;&#x442;, &#x435;&#x441;&#x442;&#x44C;
        &#x43B;&#x438; &#x443; &#x440;&#x43E;&#x43B;&#x438; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x435;
        &#x440;&#x430;&#x437;&#x440;&#x435;&#x448;&#x435;&#x43D;&#x438;&#x435;
        &#x432; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x43C;
        &#x43A;&#x430;&#x43D;&#x430;&#x43B;&#x435;</td>
    </tr>
  </tbody>
</table>

### Message

Этот тип данных описывает все доступные данные о сообщении в текстовом канале.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор сообщения |
| `contentRaw` | [Строка](syntax/expressions.md#primitivy) | Содержимое сообщения без какой-либо обработки \(как его прислал Discord\) |
| `contentDisplay` | [Строка](syntax/expressions.md#primitivy) | Содержимое сообщения, где все коды каналов, эмоций и упоминаний заменены их наименованиями |
| `contentStripped` | [Строка](syntax/expressions.md#primitivy) | Содержимое сообщения как `contentDisplay`, но дополнительно еще и без какого-либо форматирования |
| `jumpUrl` | [Строка](syntax/expressions.md#primitivy) | Ссылка быстрого перехода на это сообщение |
| `channel` | [TextChannel](types.md#textchannel) | Канал, в котором опубликовано это сообщение |
| `guild` | [Guild](types.md#guild) | Данные о сервере сообщения |
| `author` | [Member](types.md#member) | Автор этого сообщения |
| `createdAt` | [Date](functions.md#date) | Дата и время создания сообщения |
| `mentionedMembers` | [Список](syntax/expressions.md#spiski)&lt;[Member](types.md#member)&gt; | Список упоминаний участников в сообщении |
| `mentionedChannels` | [Список](syntax/expressions.md#spiski)&lt;[TextChannel](types.md#textchannel)&gt; | Список упоминаний каналов в сообщении |
| `mentionedRoles` | [Список](syntax/expressions.md#spiski)&lt;[Role](types.md#role)&gt; | Список упоминаний ролей в сообщении |
| `attachments` | [Список](syntax/expressions.md#spiski)&lt;[Attachment](types.md#attachment)&gt; | Список вложений к сообщению |

### Attachment

Этот тип данных описывает данные о вложении сообщения \(файлы, картинки, видео\).

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `id` | [Число](syntax/expressions.md#primitivy) | Уникальный идентификатор вложения |
| `createdAt` | [Date](functions.md#date) | Дата и время создание категории |
| `url` | [Строка](syntax/expressions.md#primitivy) | Ссылка на вложение |
| `proxyUrl` | [Строка](syntax/expressions.md#primitivy) | Ссылка на вложение через Discord CDN прокси |
| `fileName` | [Строка](syntax/expressions.md#primitivy) | Имя загруженного файла |
| `size` | [Число](syntax/expressions.md#primitivy) | Размер файла в байтах |
| `height` | [Число](syntax/expressions.md#primitivy) | Высота картинки/видео. `-1` для остальных типов файлов |
| `width` | [Число](syntax/expressions.md#primitivy) | Ширина картинки/видео. `-1` для остальных типов файлов |

### Embed

Этот тип данных используется для построения embed-сообщения \(панели\). Большинство методов возвращают этот же embed, поэтому можно строить цепочки вроде `withTitle('Заголовок').withDescription('Описание')`

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `empty` | [Логический](syntax/expressions.md#primitivy) | Признак того, пустая ли сейчас панель |
| `validLength` | [Логический](syntax/expressions.md#primitivy) | Признак того, допустимая ли длина содержимого панели для отправки в канал |
| `length` | [Число](syntax/expressions.md#primitivy) | Возвращает длину содержимого панели |

#### Методы

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41C;&#x435;&#x442;&#x43E;&#x434;</th>
      <th style="text-align:left">&#x41F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x44B;</th>
      <th
      style="text-align:left">&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;</th>
        <th
        style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
          <th style="text-align:center">&#x41A;&#x432;&#x43E;&#x442;&#x430;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>withContent(&#x422;&#x435;&#x43A;&#x441;&#x442;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x442;&#x435;&#x43A;&#x441;&#x442;, &#x43A;&#x43E;&#x442;&#x43E;&#x440;&#x44B;&#x439;
        &#x431;&#x443;&#x434;&#x435;&#x442; &#x43E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43B;&#x435;&#x43D;
        &#x432;&#x43D;&#x435; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438;.</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withTitle(<br />  &#x41D;&#x430;&#x438;&#x43C;&#x435;&#x43D;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x435;, <br />  URL<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>&#x41D;&#x430;&#x438;&#x43C;&#x435;&#x43D;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x435;:
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>URL (&#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;):
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x43D;&#x430;&#x438;&#x43C;&#x435;&#x43D;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x435;
        &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438; &#x438; &#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;
        &#x441;&#x441;&#x44B;&#x43B;&#x43A;&#x443;.</td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withAuthor(<br />  &#x418;&#x43C;&#x44F;, <br />  URL, <br />  IconURL<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>&#x418;&#x43C;&#x44F;:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>URL (&#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;):
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>IconURL (&#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;):
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x438;&#x43C;&#x44F; &#x430;&#x432;&#x442;&#x43E;&#x440;&#x430;, &#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;
        &#x441;&#x441;&#x44B;&#x43B;&#x43A;&#x438; &#x43D;&#x430; &#x441;&#x442;&#x440;&#x430;&#x43D;&#x438;&#x446;&#x443;
        &#x438; &#x43D;&#x430; &#x438;&#x43A;&#x43E;&#x43D;&#x43A;&#x443;</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withDescription(&#x422;&#x435;&#x43A;&#x441;&#x442;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x441;&#x43E;&#x434;&#x435;&#x440;&#x436;&#x438;&#x43C;&#x43E;&#x435;
        &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438; (&#x43E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;)</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>appendDescription(&#x422;&#x435;&#x43A;&#x441;&#x442;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x414;&#x43E;&#x43F;&#x438;&#x441;&#x44B;&#x432;&#x430;&#x435;&#x442;
        &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x439; &#x442;&#x435;&#x43A;&#x441;&#x442;
        &#x43A; &#x443;&#x436;&#x435; &#x441;&#x443;&#x449;&#x435;&#x441;&#x442;&#x432;&#x443;&#x44E;&#x449;&#x435;&#x43C;&#x443;
        &#x441;&#x43E;&#x434;&#x435;&#x440;&#x436;&#x438;&#x43C;&#x43E;&#x43C;&#x443;
        &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438; (&#x43E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x44E;)</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withThumbnail(URL)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x441;&#x441;&#x44B;&#x43B;&#x43A;&#x443; &#x43D;&#x430; &#x43A;&#x430;&#x440;&#x442;&#x438;&#x43D;&#x43A;&#x443;-&#x43C;&#x438;&#x43D;&#x438;&#x430;&#x442;&#x44E;&#x440;&#x443;</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withImage(URL)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x441;&#x441;&#x44B;&#x43B;&#x43A;&#x443; &#x43D;&#x430; &#x43F;&#x43E;&#x43B;&#x43D;&#x43E;&#x440;&#x430;&#x437;&#x43C;&#x435;&#x440;&#x43D;&#x443;&#x44E;
        &#x43A;&#x430;&#x440;&#x442;&#x438;&#x43D;&#x43A;&#x443;</td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withColor(&#x426;&#x432;&#x435;&#x442;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">
        <p>&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
          &#x446;&#x432;&#x435;&#x442; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438;,
          &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x43E;
          &#x443;&#x43A;&#x430;&#x437;&#x44B;&#x432;&#x430;&#x442;&#x44C; &#x448;&#x435;&#x441;&#x442;&#x438;&#x437;&#x43D;&#x430;&#x447;&#x43D;&#x44B;&#x439;
          &#x446;&#x432;&#x435;&#x442; &#x432; HEX, &#x43D;&#x430;&#x43F;&#x440;&#x438;&#x43C;&#x435;&#x440; <code>#FF0000</code> &#x434;&#x43B;&#x44F;
          &#x43A;&#x440;&#x430;&#x441;&#x43D;&#x43E;&#x433;&#x43E; (&#x43C;&#x43E;&#x436;&#x43D;&#x43E;
          &#x431;&#x435;&#x437; &#x440;&#x435;&#x448;&#x435;&#x442;&#x43A;&#x438;).</p>
        <p><a href="https://htmlcolorcodes.com/">https://htmlcolorcodes.com/</a>
        </p>
      </td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addField(<br />  &#x41D;&#x430;&#x438;&#x43C;&#x435;&#x43D;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x435;,<br />  &#x417;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;,<br />  &#x41E;&#x434;&#x43D;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x447;&#x43D;&#x43E;&#x435;<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>&#x41D;&#x430;&#x438;&#x43C;&#x435;&#x43D;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x435;:
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>&#x417;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>&#x41E;&#x434;&#x43D;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x447;&#x43D;&#x43E;&#x435;:
            <br
            /><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x414;&#x43E;&#x431;&#x430;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x43D;&#x43E;&#x432;&#x43E;&#x435;
        &#x43F;&#x43E;&#x43B;&#x435; &#x43A; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438;,
        &#x441; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x43C;
        &#x43D;&#x430;&#x438;&#x43C;&#x435;&#x43D;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x435;&#x43C;,
        &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;&#x43C; &#x438;
        &#x43F;&#x440;&#x438;&#x437;&#x43D;&#x430;&#x43A;&#x43E;&#x43C; &#x43E;&#x434;&#x43D;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x447;&#x43D;&#x43E;&#x441;&#x442;&#x438;.</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withFooter(<br />  &#x422;&#x435;&#x43A;&#x441;&#x442;, <br />  IconURL<br />)</code>
      </td>
      <td style="text-align:left">
        <ul>
          <li>&#x422;&#x435;&#x43A;&#x441;&#x442;:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>IconURL (&#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;):
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x442;&#x435;&#x43A;&#x441;&#x442; &#x444;&#x443;&#x442;&#x435;&#x440;&#x430;
        (&#x43F;&#x43E;&#x434;&#x432;&#x430;&#x43B;&#x430;) &#x438; &#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;
        &#x441;&#x441;&#x44B;&#x43B;&#x43A;&#x443; &#x43D;&#x430; &#x438;&#x43A;&#x43E;&#x43D;&#x43A;&#x443;</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addReaction(&#x42D;&#x43C;&#x43E;&#x446;&#x438;&#x44F;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x414;&#x43E;&#x431;&#x430;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x440;&#x435;&#x430;&#x43A;&#x446;&#x438;&#x44E;
        &#x43A; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x44E;.
        &#x420;&#x430;&#x431;&#x43E;&#x442;&#x430;&#x435;&#x442; &#x430;&#x43D;&#x430;&#x43B;&#x43E;&#x433;&#x438;&#x447;&#x43D;&#x43E;
        &#x444;&#x443;&#x43D;&#x43A;&#x446;&#x438;&#x438; <a href="functions.md#reaction">reaction</a>.</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addButton(<br />  &#x422;&#x438;&#x43F;,<br />  URL,<br />  &#x422;&#x435;&#x43A;&#x441;&#x442;,<br />  &#x42D;&#x43C;&#x43E;&#x446;&#x438;&#x44F;<br />)</code>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>&#x422;&#x438;&#x43F;:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>URL:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>&#x422;&#x435;&#x43A;&#x441;&#x442;:
            <br /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
          <li>&#x42D;&#x43C;&#x43E;&#x446;&#x438;&#x44F;
            <br />(&#x43E;&#x43F;&#x446;&#x438;&#x43E;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;):
            <br
            /><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x414;&#x43E;&#x431;&#x430;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x43A;&#x43D;&#x43E;&#x43F;&#x43A;&#x443;
        &#x43A; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x44E;.
        &#x420;&#x430;&#x431;&#x43E;&#x442;&#x430;&#x435;&#x442; &#x430;&#x43D;&#x430;&#x43B;&#x43E;&#x433;&#x438;&#x447;&#x43D;&#x43E;
        &#x444;&#x443;&#x43D;&#x43A;&#x446;&#x438;&#x438; <a href="functions.md#button">button</a>.</td>
      <td
      style="text-align:center"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>withDate(&#x414;&#x430;&#x442;&#x430;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>,
        <br
        /><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>,
        <br
        /><a href="functions.md#date">Date</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">
        <p>&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
          &#x434;&#x430;&#x442;&#x443; &#x432; &#x43F;&#x43E;&#x434;&#x432;&#x430;&#x43B;&#x435;
          (&#x444;&#x443;&#x442;&#x435;&#x440;&#x435;) &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438;.
          &#x41C;&#x43E;&#x436;&#x435;&#x442; &#x43F;&#x440;&#x438;&#x43D;&#x438;&#x43C;&#x430;&#x442;&#x44C;:</p>
        <ul>
          <li>&#x427;&#x438;&#x441;&#x43B;&#x43E; (Unix timestamp);</li>
          <li>&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x443; &#x432; &#x444;&#x43E;&#x440;&#x43C;&#x430;&#x442;&#x435;:
            <br
            /><code>yyyy-MM-dd&apos;T&apos;HH:mm:ss.SSSZ</code>
          </li>
          <li>&#x414;&#x430;&#x442;&#x443; &#x438;&#x437; &#x434;&#x440;&#x443;&#x433;&#x438;&#x445;
            &#x442;&#x438;&#x43F;&#x43E;&#x432;</li>
        </ul>
      </td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addBlankField(&#x41E;&#x434;&#x43D;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x447;&#x43D;&#x43E;&#x435;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x414;&#x43E;&#x431;&#x430;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x43F;&#x443;&#x441;&#x442;&#x43E;&#x435;
        &#x43F;&#x43E;&#x43B;&#x435; &#x441; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x43C;
        &#x43F;&#x440;&#x438;&#x437;&#x43D;&#x430;&#x43A;&#x43E;&#x43C; &#x43E;&#x434;&#x43D;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x447;&#x43D;&#x43E;&#x441;&#x442;&#x438;.</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>clearFields()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x41E;&#x447;&#x438;&#x449;&#x430;&#x435;&#x442; &#x432;&#x441;&#x435;
        &#x43F;&#x43E;&#x43B;&#x44F; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438;</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>clear()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x41E;&#x447;&#x438;&#x449;&#x430;&#x435;&#x442; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x44C;
        &#x43F;&#x43E;&#x43B;&#x43D;&#x43E;&#x441;&#x442;&#x44C;&#x44E;</td>
      <td
      style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>error()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x41F;&#x440;&#x435;&#x434;&#x443;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438; &#x43A;&#x440;&#x430;&#x441;&#x43D;&#x44B;&#x439;
        &#x446;&#x432;&#x435;&#x442; &#x438; &#x437;&#x430;&#x433;&#x43E;&#x43B;&#x43E;&#x432;&#x43E;&#x43A;
        &#x43E;&#x448;&#x438;&#x431;&#x43A;&#x438; (&#x434;&#x43B;&#x44F; &#x443;&#x434;&#x43E;&#x431;&#x441;&#x442;&#x432;&#x430;
        &#x43F;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x435;&#x43D;&#x438;&#x44F;
        &#x43E;&#x448;&#x438;&#x431;&#x43E;&#x43A;)</td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>deleteAfterSec(&#x421;&#x435;&#x43A;&#x443;&#x43D;&#x434;&#x44B;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>
      </td>
      <td style="text-align:left"><a href="types.md#embed">Embed</a>
      </td>
      <td style="text-align:left">&#x423;&#x441;&#x442;&#x430;&#x43D;&#x430;&#x432;&#x43B;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x432;&#x440;&#x435;&#x43C;&#x44F; &#x432; &#x441;&#x435;&#x43A;&#x443;&#x43D;&#x434;&#x430;&#x445;,
        &#x447;&#x435;&#x440;&#x435;&#x437; &#x43A;&#x43E;&#x442;&#x43E;&#x440;&#x43E;&#x435;
        &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x44C; &#x431;&#x443;&#x434;&#x435;&#x442;
        &#x443;&#x434;&#x430;&#x43B;&#x435;&#x43D;&#x430; &#x43F;&#x43E;&#x441;&#x43B;&#x435;
        &#x43E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43A;&#x438;</td>
      <td style="text-align:center">-</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>send()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43B;&#x44F;&#x435;&#x442;
        &#x432; &#x44D;&#x442;&#x43E;&#x442; &#x43A;&#x430;&#x43D;&#x430;&#x43B;
        &#x44D;&#x442;&#x443; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x44C;. &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
        &#x435;&#x441;&#x43B;&#x438; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x435;
        &#x431;&#x44B;&#x43B;&#x43E; &#x443;&#x441;&#x43F;&#x435;&#x448;&#x43D;&#x43E;
        &#x43E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43B;&#x435;&#x43D;&#x43E;.</td>
      <td
      style="text-align:center">2*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>update(Id)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">
        <p>&#x41E;&#x431;&#x43D;&#x43E;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x435;
          &#x441; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x43C;
          &#x438;&#x434;&#x435;&#x43D;&#x442;&#x438;&#x444;&#x438;&#x43A;&#x430;&#x442;&#x43E;&#x440;&#x43E;&#x43C;
          &#x43D;&#x430; &#x44D;&#x442;&#x443; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x44C;.
          &#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442; <code>true</code>,
          &#x435;&#x441;&#x43B;&#x438; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x435;
          &#x431;&#x44B;&#x43B;&#x43E; &#x443;&#x441;&#x43F;&#x435;&#x448;&#x43D;&#x43E;
          &#x43E;&#x442;&#x440;&#x435;&#x434;&#x430;&#x43A;&#x442;&#x438;&#x440;&#x43E;&#x432;&#x430;&#x43D;&#x43E;.</p>
        <p></p>
        <p><b>&#x41C;&#x43E;&#x436;&#x43D;&#x43E; &#x440;&#x435;&#x434;&#x430;&#x43A;&#x442;&#x438;&#x440;&#x43E;&#x432;&#x430;&#x442;&#x44C; &#x442;&#x43E;&#x43B;&#x44C;&#x43A;&#x43E; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x44F; &#x441;&#x430;&#x43C;&#x43E;&#x433;&#x43E; &#x431;&#x43E;&#x442;&#x430;!</b>
        </p>
      </td>
      <td style="text-align:center">2*</td>
    </tr>
  </tbody>
</table>

\* У всех методов отправки сообщений общий счётчик квоты вызовов.

### AttributesStorage

Это динамический тип, свойствами которого являются соответствующие [атрибуты](types.md#attribute) участника.

{% hint style="warning" %}
В рамках выполнения одного шаблона сообщения допускается обращение максимум к 5 атрибутам участника.
{% endhint %}

### Attribute

Этот тип данных описывает атрибут участника. С помощью атрибутов можно хранить какие-либо собственные привязанные к участникам данные.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `value` | [Строка](syntax/expressions.md#primitivy),  [Число](syntax/expressions.md#primitivy), [Логический](syntax/expressions.md#primitivy) | Текущее значение атрибута |
| `updatedAt` | [Date](functions.md#date) | Дата последнего обновления атрибута |

#### Методы

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41C;&#x435;&#x442;&#x43E;&#x434;</th>
      <th style="text-align:left">&#x41F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x44B;</th>
      <th
      style="text-align:left">&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;</th>
        <th
        style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
          <th style="text-align:center">&#x41A;&#x432;&#x43E;&#x442;&#x430;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>update(&#x417;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>,
        <br
        /><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>,
        <br
        /><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x421;&#x442;&#x440;&#x43E;&#x43A;&#x430;</a>,
        <br
        /><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>,
        <br
        /><a href="syntax/expressions.md#primitivy">&#x41B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x439;</a>
      </td>
      <td style="text-align:left">&#x41E;&#x431;&#x43D;&#x43E;&#x432;&#x43B;&#x44F;&#x435;&#x442; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;
        &#x430;&#x442;&#x440;&#x438;&#x431;&#x443;&#x442;&#x430; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x439;
        &#x441;&#x442;&#x440;&#x43E;&#x43A;&#x43E;&#x439;, &#x447;&#x438;&#x441;&#x43B;&#x43E;&#x43C;
        &#x438;&#x43B;&#x438; &#x43B;&#x43E;&#x433;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;&#x43C;
        &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;&#x43C;.
        <br />&#x41C;&#x430;&#x43A;&#x441;&#x438;&#x43C;&#x430;&#x43B;&#x44C;&#x43D;&#x430;&#x44F;
        &#x434;&#x43B;&#x438;&#x43D;&#x430; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x44F;
        2000 &#x441;&#x438;&#x43C;&#x432;&#x43E;&#x43B;&#x43E;&#x432;.
        <br />&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;
        &#x44D;&#x442;&#x43E; &#x436;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;.</td>
      <td
      style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>increment(&#x427;&#x438;&#x441;&#x43B;&#x43E;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>
      </td>
      <td style="text-align:left">&#x423;&#x432;&#x435;&#x43B;&#x438;&#x447;&#x438;&#x432;&#x430;&#x435;&#x442;
        &#x447;&#x438;&#x441;&#x43B;&#x43E;&#x432;&#x43E;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;
        &#x43D;&#x430; &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x435;
        &#x447;&#x438;&#x441;&#x43B;&#x43E;.
        <br />&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;
        &#x43D;&#x43E;&#x432;&#x43E;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;.
        <br
        />&#x41E;&#x442;&#x441;&#x447;&#x435;&#x442; &#x43D;&#x430;&#x447;&#x438;&#x43D;&#x430;&#x435;&#x442;&#x441;&#x44F;
        &#x441; 0 &#x435;&#x441;&#x43B;&#x438; &#x442;&#x435;&#x43A;&#x443;&#x449;&#x435;&#x435;
        &#x445;&#x440;&#x430;&#x43D;&#x438;&#x43C;&#x43E;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;
        &#x43D;&#x435; &#x447;&#x438;&#x441;&#x43B;&#x43E;.</td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>decrement(&#x427;&#x438;&#x441;&#x43B;&#x43E;)</code>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>
      </td>
      <td style="text-align:left"><a href="syntax/expressions.md#primitivy">&#x427;&#x438;&#x441;&#x43B;&#x43E;</a>
      </td>
      <td style="text-align:left">
        <p>&#x423;&#x43C;&#x435;&#x43D;&#x44C;&#x448;&#x430;&#x435;&#x442; &#x447;&#x438;&#x441;&#x43B;&#x43E;&#x432;&#x43E;&#x435;
          &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435; &#x43D;&#x430;
          &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x43E;&#x435; &#x447;&#x438;&#x441;&#x43B;&#x43E;.
          <br
          />&#x412;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;
          &#x43D;&#x43E;&#x432;&#x43E;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;.</p>
        <p>&#x41E;&#x442;&#x441;&#x447;&#x435;&#x442; &#x43D;&#x430;&#x447;&#x438;&#x43D;&#x430;&#x435;&#x442;&#x441;&#x44F;
          &#x441; 0 &#x435;&#x441;&#x43B;&#x438; &#x442;&#x435;&#x43A;&#x443;&#x449;&#x435;&#x435;
          &#x445;&#x440;&#x430;&#x43D;&#x438;&#x43C;&#x43E;&#x435; &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;
          &#x43D;&#x435; &#x447;&#x438;&#x441;&#x43B;&#x43E;.</p>
      </td>
      <td style="text-align:center">1*</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>clear()</code>
      </td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">&#x41E;&#x447;&#x438;&#x449;&#x430;&#x435;&#x442; &#x430;&#x442;&#x440;&#x438;&#x431;&#x443;&#x442;
        &#x438; &#x443;&#x434;&#x430;&#x43B;&#x44F;&#x435;&#x442; &#x438;&#x437;
        &#x431;&#x430;&#x437;&#x44B; &#x434;&#x430;&#x43D;&#x43D;&#x44B;&#x445;.</td>
      <td
      style="text-align:center">1</td>
    </tr>
  </tbody>
</table>

\* У всех методов обновления значения общий счётчик квоты вызовов \(в рамках одного атрибута\).

### Arguments

Этот тип данных описывает аргументы сообщения вызова пользовательской команды.

#### Свойства

| Свойство | Тип | Описание |
| :--- | :--- | :--- |
| `value` | [Строка](syntax/expressions.md#primitivy) | Исходная строка вызова пользовательской команды |
| `args` | [Список](syntax/expressions.md#spiski)&lt;[Строка](syntax/expressions.md#primitivy)&gt; | Список аргументов, извлеченных из строки и разделенных пробелом |

#### Методы

| Метод | Параметры | Возвращает | Описание |
| :--- | :--- | :--- | :--- |
| `get(Номер)` | [Число](syntax/expressions.md#primitivy) | [Строка](syntax/expressions.md#primitivy) | Получение аргумента по указанному номеру |
| `after(Номер)` | [Число](syntax/expressions.md#primitivy) | [Строка](syntax/expressions.md#primitivy) | Получение всех аргументов, начиная с указанного номера включительно |
| `before(Номер)` | [Число](syntax/expressions.md#primitivy) | [Строка](syntax/expressions.md#primitivy) | Получение всех аргументов от первого до указанного включительно |
| `range(   Начало,   Конец )` | [Число](syntax/expressions.md#primitivy) | [Строка](syntax/expressions.md#primitivy) | Получение диапазона аргументов |

{% hint style="info" %}
Отсчет номера аргумента начинается с 1.
{% endhint %}

### Permission

Здесь описан список всех возможных разрешений. Их нужно передавать в методы как [строки](syntax/expressions.md#primitivy).

| Разрешение | Описание |
| :--- | :--- |
| `CREATE_INSTANT_INVITE` | Создать экспресс-приглашение |
| `KICK_MEMBERS` | Выгнать участников |
| `BAN_MEMBERS` | Банить участников |
| `ADMINISTRATOR` | Администратор |
| `MANAGE_CHANNEL` | Управление каналами |
| `MANAGE_SERVER` | Управление сервером |
| `MESSAGE_ADD_REACTION` | Добавлять реакции |
| `VIEW_AUDIT_LOGS` | Просмотр журнала аудита |
| `PRIORITY_SPEAKER` | Приоритет говорящего |
| `VIEW_GUILD_INSIGHTS` | Просмотр аналитики сервера |
| `VIEW_CHANNEL` | Читать текстовые и видеть голосовые каналы |
| `MESSAGE_READ` | Читать сообщения |
| `MESSAGE_WRITE` | Отправлять сообщения |
| `MESSAGE_TTS` | Отправлять TTS-сообщения |
| `MESSAGE_MANAGE` | Управлять сообщениями |
| `MESSAGE_EMBED_LINKS` | Встраивать ссылки |
| `MESSAGE_ATTACH_FILES` | Прикреплять файлы |
| `MESSAGE_HISTORY` | Читать историю сообщений |
| `MESSAGE_MENTION_EVERYONE` | Упомянуть всех |
| `MESSAGE_EXT_EMOJI` | Использовать внешние эмодзи |
| `USE_SLASH_COMMANDS` | Использовать слеш-команды |
| `VOICE_STREAM` | Транслировать |
| `VOICE_CONNECT` | Подключаться к голосовому чату |
| `VOICE_SPEAK` | Говорить в голосовом чате |
| `VOICE_MUTE_OTHERS` | Отключить голос участникам |
| `VOICE_DEAF_OTHERS` | Отключить звук участникам |
| `VOICE_MOVE_OTHERS` | Переместить участников |
| `VOICE_USE_VAD` | Использовать режим активации по голосу |
| `NICKNAME_CHANGE` | Изменить свой никнейм |
| `NICKNAME_MANAGE` | Управление никнеймами |
| `MANAGE_ROLES` | Управление ролями |
| `MANAGE_PERMISSIONS` | Управление правами |
| `MANAGE_WEBHOOKS` | Управление вебхуками |
| `MANAGE_EMOTES` | Управление эмодзи |

