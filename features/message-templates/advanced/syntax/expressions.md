---
description: 'Expressions, constants, primitive data types'
---

# Expressions

Expressions are the logic building blocks, they allow you to express a value. From the basic constants to binary and ternary operations, expressions give the power to specify a value.

### Literals <a id="literals"></a>

Literals are the most basic expressions, check the table below:

| Name | Example |
| :--- | :--- |
| Float | `-1.5`, `5.7`, `1.0` |
| Integer | `-10`, `56`, `0` |
| Null Reference | `null` |
| Boolean | `true` or `false` |
| String | `"string in double brackets"` `'apostrophe string'` |
| Character | `'g'` |

### Identifiers <a id="identifiers"></a>

Identifier is the name in Template Engine. It can contain alphanumeric characters and also underscores, but cannot start with digits.

### Lists <a id="lists"></a>

There is the one way to specify a list in Template Engine by enumeration, you need to provide every single element of the list, as shown below:

```text
[1, 2, 3]
```

### Maps <a id="maps"></a>

It is also possible to represent collections of key and value pairs, so called maps, where keys can either be Identifiers or Strings and values can take form of any kind of expression:

```javascript
{ key1: 'value1', 'key 2': 'value2' }
```

Keep in mind that identifiers used to represent the key elements are not used as variable placeholders, instead, they are converted to their String representation. For example, the identifier `key1` shown above will be converted to the String value `"key1"`.

### List or Map Value Access <a id="access"></a>

Whenever you need to access either a list element or map value, Template Engine comes with the value access expression. With such expression you can access the value given the key. Note that, for lists, the key is the position of the element in the list starting at zero.

```text
list[0]
map["key1"]
```

### Keywords <a id="keywords"></a>

Template Engine has some reserved identifiers, such identifiers are the building blocks of more complex constructs. Below there is the list of the native reserved identifiers:

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p></p>
        <ul>
          <li><code>set</code>
          </li>
          <li><code>global</code>
          </li>
          <li><code>if</code>
          </li>
          <li><code>elseif</code>
          </li>
          <li><code>else</code>
          </li>
          <li><code>endif</code>
          </li>
          <li><code>for</code>
          </li>
          <li><code>endfor</code>
          </li>
          <li><code>true</code>
          </li>
          <li><code>false</code>
          </li>
          <li><code>empty</code>
          </li>
          <li><code>return</code>
          </li>
        </ul>
      </th>
      <th style="text-align:left">
        <p></p>
        <ul>
          <li><code>in</code>
          </li>
          <li><code>as</code>
          </li>
          <li><code>do</code>
          </li>
          <li><code>verbatim</code>
          </li>
          <li><code>filter</code>
          </li>
          <li><code>endfilter</code>
          </li>
          <li><code>null</code>
          </li>
          <li><code>is</code>
          </li>
          <li><code>not</code>
          </li>
          <li><code>with</code>
          </li>
          <li><code>require</code>
          </li>
          <li><code>returning</code>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

### Unary Operators <a id="unary"></a>

Unary operators by definition only need one argument, Template Engine comes with only two built in unary operators, they are `not` and `-`.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Symbol</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">P*</th>
      <th style="text-align:left">Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>-</code>
      </td>
      <td style="text-align:left">&#x41C;&#x435;&#x43D;&#x44F;&#x435;&#x442; &#x437;&#x43D;&#x430;&#x43A;</td>
      <td
      style="text-align:left">5</td>
        <td style="text-align:left"><code>-(-1)</code> outputs <code>1</code>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>not</code>
      </td>
      <td style="text-align:left">&#x41E;&#x442;&#x440;&#x438;&#x446;&#x430;&#x43D;&#x438;&#x435;</td>
      <td
      style="text-align:left">10</td>
        <td style="text-align:left">
          <p><code>not false</code> outputs <code>true</code>
          </p>
          <p><code>not true</code> outputs <code>false</code>
          </p>
        </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
\*Precedence is the order or operator calculation , the lower the precedence, the higher the priority.
{% endhint %}

### Binary Operators <a id="binary"></a>

Template Engine comes with several built in binary operators:

| Symbol | P\* | Description | Пример |
| :--- | :--- | :--- | :--- |
| `.` | 1 | Access inner properties of objects | `[1, 2].size` outputs `2` |
| `*` | 5 | Multiplies two values | `2.2 * 2.2` outputs `4.84` |
| `**` | 5 | Multiplies the integer part of two values | `2.2 ** 2.2` outputs `4` |
| `/` | 5 | Divides two values | `5.0 / 2.0` outputs `2.5` |
| `//` | 5 | Divides the integer part of two values | `5.0 // 2.0` outputs `3` |
| `%` | 5 | Gets the integer division remainder | `5 % 2` outputs `1` |
| `+` | 10 | Sums two values | `5 + 2` outputs `7` |
| `-` | 10 | Subtracts two values | `5 - 2` outputs `3` |
| `~` | 12 | Concatenates two strings | `"5" ~ "2"` outputs `"52"` |
| `<` | 15 | Compares two values, checking whether the first is lower than the second | `1 < 2` outputs `true` `1 < 1` outputs `false` |
| `<=` | 15 | Compares two values, checking whether the first is lower or equal than the second | `2 <= 2` outputs `true` `2 < 1` outputs `false` |
| `>` | 15 | Compares two values, checking whether the first is higher than the second | `2 > 1` outputs `true` `2 > 2` outputs `false` |
| `>=` | 15 | Compares two values, checking whether the first is higher or equal than the second | `2 >= 2` outputs `true` `2 >= 3` outputs `false` |
| `in` | 15 | Checks whether the second value contains the first one | `5 in [2]` outputs `false` |
| `==` | 20 | Compares two values, checking whether they are equal or not | `true == false` outputs `false` `false == false` outputs `true` |
| `!=` | 20 | Compares two values, checking whether they are different or not | `true != false` outputs `true` `false != false` outputs `false` |
| `and` | 25 | Conjunction boolean operator | `true and false` outputs `false` `true and true` outputs `true` |
| `or` | 25 | Disjunction boolean operator | `true or false` outputs `true` `false or false` outputs `false` |
| `|` | 30 | Uses the first argument as parameter for the second argument. Note that, composition forces the second argument to be a function | `-5 | abs` outputs `5` |

{% hint style="info" %}
\*Precedence is the order or operator calculation , the lower the precedence, the higher the priority.
{% endhint %}

### Ternary Operator <a id="ternary"></a>

Template Engine only contains one ternary operator. It allows to fork the logic based on a boolean expression, as exemplified below:

```text
{{ expr ? 1 : 2 }}
```

 Such expression will output `1` if the variable `expr` is true, or `2` if the variable is false.

### Elvis Operator <a id="elvis"></a>

Template Engine supports elvis operator that returns its first operand if that operand evaluates to a true value according [Type Convert](type-convert.md), and otherwise evaluates and returns its second operand.

```text
{{ <expression A> ?: <expression B> }}
```

This operator is very useful to return a "default" value for expressions.

### Text Expressions <a id="test"></a>

Test expressions are a complex predicate construct, they return a boolean value as result.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Null</td>
      <td style="text-align:left">Checks whether a value is null or not</td>
      <td style="text-align:left"><code>1 is null</code> outputs <code>false</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Divisible</td>
      <td style="text-align:left">Checks if a value is divisible by another</td>
      <td style="text-align:left"><code>2 is divisible by 1</code> outputs <code>true</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Same As</td>
      <td style="text-align:left">Checks whether two objects are, actually, the same</td>
      <td style="text-align:left"><code>1 is same as 2</code> outputs <code>false</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Function based</td>
      <td style="text-align:left">This construct is based on the available list of <a href="../functions.md">functions</a>.</td>
      <td
      style="text-align:left">
        <p><code>4 is defined</code> outputs <code>true;</code>
        </p>
        <p><code>&apos;test&apos; is number</code> outputs <code>false</code>.</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">Is Not</td>
      <td style="text-align:left">All test constructs listed before can be negated with the <code>is not</code> constructor.</td>
      <td
      style="text-align:left"><code>4 is not defined</code> outputs <code>false</code>
        </td>
    </tr>
  </tbody>
</table>

### Selection Operator <a id="selection"></a>

The selection operator is used to access a properties or object or invoke its functions. You can find available properties and functions in the [Data Types](../types.md) and [Input Data](../variables.md) articles.

```text
guild.name
channel.sendMessage('hello!')
```

Selection operator is also used in maps as well to get the value represented by given key.

