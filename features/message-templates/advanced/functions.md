---
description: Template Engine Global Functions
---

# Functions

## Binary Functions <a id="binary"></a>

### `defined`

The `defined` function is useful to check if a given expression is defined or not. It returns `true` if the given expression is defined, `false` otherwise.

```csharp
{% if (defined([1, 2][5])) %}YES{% else %}NO{% endif %}
```

 The previous example will output `NO` because index `5` of list `[1, 2]` is undefined.

### `even`

This function is quite simple, it is expecting one number as argument and it returns `true` when that number is even, `false` otherwise.

```csharp
{% if (even(2)) %}A{% else %}B{% endif %}
```

The previous example prints `A`.

### `odd`

This is the opposite of the `even` function, it is expecting one number as argument and it returns `true` when that number is odd, `false` otherwise.

```csharp
{% if (odd(2)) %}A{% else %}B{% endif %}
```

 The previous example prints `B`.

### `iterable`

The `iterable` function allows to check if a given argument is a collection for loops can iterate over, or index/map selections can be used.

```csharp
{% if (iterable(2)) %}A{% else %}B{% endif %}
```

The previous template will print `B` because `2` is not a map or list so it is not iterable.

### `number`

The `number` function allows to check if a given argument is a number or available for automatic conversion to number according to [Type Convert](syntax/type-convert.md).

```csharp
{% if (number(2)) %}A{% else %}B{% endif %}
```

The previous template will print `A` because `2` is number.

### `empty`

The empty function returns a boolean value. As input it is expecting a generic object, it returns `true` if the given input falls in one of the following scenarios:

* `null`
* `Undefined`
* non-empty list
* non-empty map
* non-zero number

```csharp
{% if (empty([1, 2])) %}A{% else %}B{% endif %}
```

The previous example produces `B` as `[1, 2]` is not an empty list.

## Math Functions <a id="math"></a>

### `abs`

Mathematical function allowing to get the absolute value of an expression. For example, `{{ abs(-1) }}` will produce `1`. It is expecting only one number argument.

### `round`

The round function allowing to round a given number to integer. An optional strategy can be specified as second argument:

* `'CEIL'` - round up;
* `'FLOOR'` - round down.

```csharp
{{ round(1.3, 'CEIL') }}
```

The previous example will produce `2`. Note that the strategy selection is case insensitive, so one can either specify `'CEIL'` or `'ceil'`. If the second argument is not specified half down will be applied.

## String Functions <a id="string"></a>

### `number_format`

The `number_format` allowing to format a given number with specific symbols for the grouping and decimal separators, also the number of fractional digits. This function expects at least one argument and can receive up to four arguments. The list of arguments is presented below by the order they are expected:

1. The number to be formatted
2. The number of fractional digits \(optional\)
3. The decimal separator \(optional\)
4. The grouping separator \(optional\)

```csharp
{{ number_format(11000.136, 2, '.', ' ') }}
```

The previous example will produce `11 000.14`.

### `capitalize`

The capitalize function is expecting one argument and will capitalize the string.

```csharp
{{ capitalize('hello world') }}
```

The previous template will render as `Hello world` which is the result of capitalizing the first word.

### `format`

The `format` function receives an arbitrary number of arguments where the first is the template parameter \(converted to a String\) and the remaining arguments is provided as the format model values. Mode detailed information about format you can find on the [Internet](https://dzone.com/articles/java-string-format-examples).

```csharp
{{ format('hello %s! %s', 'world', 123) }}
```

The previous example will print `hello world! 123`.

### `lower`

Lowers the case of the string provided.

```csharp
{{ lower('JUNIPERBOT') }}
```

The previous example will print `juniperbot`.

### `upper`

Changes the case of the string provided by turning all into capitals.

```csharp
{{ upper('juniperbot') }}
```

The previous example will print `JUNIPERBOT`.

### `replace`

The `replace` function allows to specify a string and a map of replacements replacing all the ocurrences of the keys in the provided map by their respective value.

```csharp
{{ replace('Hello %name%', { '%name%': 'world' }) }}
```

The previous example will produce `Hello world` as output.

### `split`

This function expects two arguments, using the second argument provided to split the first one into a collection.

A split argument can be a regular expression.

```csharp
{{ split('juniper-bot', '-') }}
```

The previous example will return `[juniper, bot]`.

### `title`

The `title` function is expecting one string argument, capitalizing the first letter of all words present in it.

```csharp
{{ title('hello world') }}
```

The previous example will produce `Hello World`.

### `trim`

This function removes any whitespace characters from the beginning and/or ending of the given argument.

```csharp
{{ trim('  Hello World  ') }}
```

The previous example will produce `Hello World` without whitespaces.

### `startsWith`

This function checks if the first string argument starts with the second string argument.

```csharp
{{ startsWith('hello', 'he') }}
```

The previous example will produce `true` because `hello` starts with `he`. 

It can also accept a third boolean parameter that enables case-insensitive check:

```csharp
{{ startsWith('HELLO', 'he', true) }}
```

The previous example will produce `true` because `HELLO` starts with `he` case-insensitive. 

### `endsWith`

This function checks if the first string argument ends with the second string argument.

```csharp
{{ endsWith('hello', 'lo') }}
```

The previous example will produce `true` because `hello` ends with `lo`. 

It can also accept a third boolean parameter that enables case-insensitive check:

```csharp
{{ endsWith('hello', 'LO', true) }}
```

The previous example will produce `true` because `hello` ends with `LO` case-insensitive. 

### `contains`

This function checks if the first string argument contains the second string argument as substring.

```csharp
{{ contains('Hey there!', 'there') }}
```

The previous example will produce `true`  because `Hey there!` contains substring `there`. 

It can also accept a third boolean parameter that enables case-insensitive check:

```csharp
{{ contains('Hey THERE!', 'there', true) }}
```

The previous example will produce `true` because `Hey THERE!` contains substring `there` case-insensitive.

### `plural`

This function will help you to choose the correct plural form of a word or phrase depending on the specified number and language specifed \(cardinal numbers\). The command accepts up to eight arguments, depending on the selected language. 

First two arguments are number and language \(`en` - English, `ru` - Russian\). Others depends on language selected:

#### English

* Singular form 
* Plural form

```csharp
2 {{ plural(2, 'en', 'day', 'days') }}
```

The previous example will produce `2 days`.

#### Russian

* Variation for 1, 21, 31, 41, 51, 61, 71, 81, 101, 1001 \(1 день, 51 день\)
* Variation for 2~4, 22~24, 32~34, 42~44, 52~54, 62, 102, 1002 \(2 дня, 33 дня\)
* Variation for 0, 5~19, 100, 1000, 10000, 100000, 1000000 \(0 дней, 7 дней, 100 дней\)
* General genitive case \(1.5 дня\)

```csharp
2 {{ plural(2, 'ru', 'день', 'дня', 'дней', 'дня') }}
```

The previous example will produce `2 дня`.

## Mixed Functions <a id="mixed"></a>

### `random`

This function will return a random list element or number from the range specified.

```csharp
{{ random(['one', 'two', 'three']) }}
```

The previous example will produce `one`, `two` or `three` randomly.

```csharp
{{ random(10, 20) }}
```

The previous example will produce a random number from 10 to 20 inclusive.

### `first`

The `first` function returns the first element of a collection or string. If the argument provided is not a collection or a string, it will just return the input argument. If the given argument is an empty list or string, then it returns `Undefined`.

```csharp
{{ first([1, 2]) }}
```

The previous example will produce `1`.

### `last`

The `last` function returns the last element of a collection or string. If the argument provided is not a collection or a string, it will just return the input argument. If the given argument is an empty list or string, then it returns `Undefined`.

```csharp
{{ last([1, 2]) }}
```

The previous example will produce `2`.

### `reverse`

The `reverse` function reverses the order of the elements in a given collection or string. If no collection neither string is provided then it returns the given argument.

```csharp
{{ reverse([1, 2]) }}
```

The previous example will produce `[2, 1]`.

### `default`

The `default` function is expecting two arguments. It returns the second argument if the first argument is either `null` or `Undefined`.

```css
{{ default(null, 'Hello') }} {{ default(undefinedVariable, 'World') }}
```

The previous example will produce `Hello World`, because `undefinedVariable` is not defined.

### `length`

The `length` function returns the length of a given collection or string. If neither a collection or string is provided then it returns `0` for both `null` and `Undefined`, otherwise `1` will be the result.

```csharp
{{ length([1, 2]) }}
{{ length(null) }}
{{ length(9) }}
```

The previous examples will print respectively `2`, `0` and `1`.

## Lists and Maps <a id="lists-maps"></a>

### `batch`

The `batch` function splits a given list in equally sized groups of items. It expects two or three arguments:

* A list as first argument;
* The second argument is the group size;
* There is also an optional third argument used as padding, that is, if the last group is incomplete, the third argument will be used to fill it.

```csharp
{{ batch([1,2,3], 2) }}
```

The previous example will output `[[1, 2], [3]]`.

```csharp
{{ batch([1,2,3], 2, 0) }}
```

The previous example, now with the padding argument, will output `[[1, 2], [3, 0]]`.

### `concat` or `concatenate`

This function allows to concatenate a set of strings. It is expecting an arbitrary number of arguments \(varargs\).

```csharp
{{ concat('1', '+', '1', '=', '2') }}
```

The previous example will output `1+1=2`.

### `join`

The `join` function provides functionality somehow similar to the `concat` function, however they have some differences. To start with, `join` takes only one or two arguments, where the first argument is expected to be a list and the second, optional, argument a string to be used as the separator. If second argument is not specified, the comma with space is used:  `,`.

```c
{{ join([1, null, 2], '|') }}
```

The previous example will print `1|2`. Note that, `join` function ignores `null` values.

### `keys`

The `keys` function can be used to expose the collection of keys for a given collection.

```csharp
{{ keys(['A', 'B']) }}
```

The previous example will produce `[1, 2]`.

### `slice`

This function is expecting three arguments, where the first argument can either be a string or a collection, and an integer as second and third arguments.

```csharp
{{ slice("123", 1, 1) }}
```

```csharp
{{ slice([1, 2, 3], 0, 2) }}
```

The second argument is the index position the slice will start from \(inclusive\), where the third argument is the length of the slice. As shown in the previous two examples, the result will be `"2"` and `[1, 2]` respectively. Note that, slice is smart enough to handle boudary cases, for example:

```csharp
{{ slice("123", 2, 3) }}
```

```csharp
{{ slice("123", 5, 1) }}
```

The previous examples will still return a slice, depending on the number of characters or items provided in the first argument, the previous examples would then resolve the slice to `"3"` and `""`.

### `sort`

The `sort` function can be used to sort elements of a given collection in ascending order.

```csharp
{{ sort([1, 3, 2]) }}
```

The previous example will produce `[1, 2, 3]`.

## Other Functions <a id="other"></a>

### `date`

The `date` function formats the date specified in the format you need. It accepts up to three arguments:

* Date object or string `'now'` to format current date;
* \(Optional\) Date format based on Java `SimpleDateFormat`. Check [this](http://www.sdfonlinetester.info/) page for more details about the format;
* \(Optional\) Timezone in format of [TZ Database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

```csharp
{{ date('now', 'EEE, d MMM yyyy HH:mm:ss z', 'Europe/Moscow') }}
```

The previous example will produce `Tue, 22 Jun 2021 04:04:05 MSK`.

{% hint style="info" %}
* If no timezone specified, the default server timezone is used. You can configure it in [server's dashboard](../../../#configure);
* Date format from the example above is the default date format used if no second argument specified.
{% endhint %}

### `reaction`

The `reaction` function will add a reaction with the specified emotion to resulting message. It accepts one argument of emotion in the following formats:

* `🦊` - Unicode-character;
* `:fox_face:` - name of emotion including default and server's emojis;
* `<a:foxwaggy:695917473874051112>` - custom emoji code.

```csharp
{% do reaction(':fox_face:') %}
```

{% hint style="success" %}
Only one reaction can be added to the message. Servers with [active bonuses](https://juniper.bot/donate) can add up to 5 reactions.
{% endhint %}

### `button`

The `button` function will add a specified button to resulting message. It accepts four string arguments.

* Type is the first argument \(Currently only `LINK` is supported\);
* The second argument is link;
* The third argument is content;
* \(Optional\) The fourth argument is emote.

```csharp
{% do button('LINK', 'https://juniper.bot/', 'Website', '🦊') %}
```

