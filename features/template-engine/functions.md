---
description: Описание всех доступных функций
---

# Функции

## Логические функции

### `defined`

Данная функция полезна для проверки определено ли указанное выражение или нет. Возвращает `true` если выражение определено и `false` в противном случае.

```csharp
{% if (defined([1, 2][5])) %}YES{% else %}NO{% endif %}
```

Предыдущий пример распечатает `NO`, так как индекс `5` списка `[1, 2]` не определен.

### `even`

Эта функция очень простая, она ожидает число и возвращает `true`, если это число чётное и `false`, если нечётное.

```csharp
{% if (even(2)) %}A{% else %}B{% endif %}
```

Предыдущий пример распечатает `A`, так как 2 - чётное число.

### `odd`

Это противоположная `even` функция. Она ожидает число и возвращает `true`, если число нечётное и `false`, если чётное.

```csharp
{% if (odd(2)) %}A{% else %}B{% endif %}
```

Предыдущий пример распечатает `B`, так как 2 - чётное число.

### `iterable`

Эта функция позволяет проверить, является ли аргумент допустимым для итераций объектом \(список или карта\).

```csharp
{% if (iterable(2)) %}A{% else %}B{% endif %}
```

Предыдущий пример распечатает `B`, так как `2` не список и не карта, а простое число.

### `empty`

Функция ожидает любой объект и возвращает `true`, если аргумент являетс:

* `null`
* `Undefined`
* Пустым списком
* Пустой картой
* Числом, отличным от 0

```csharp
{% if (empty([1, 2])) %}A{% else %}B{% endif %}
```

Предыдущий пример распечатает `B`, так как `[1, 2]` - не пустой список.

## Математические функции

### `abs`

Математическая функция, позволяющая получить модуль выражения. Например, `{{ abs(-1) }}` выведет `1`. Ожидает только один аргумент-число.

### `round`

Функция округления дробного числа к целому. Опционально можно указать стратегию округления вторым аргументом:

* `'CEIL'` - округление до большего целого;
* `'FLOOR'` - округление до меньшего целого.

```csharp
{{ round(1.3, 'CEIL') }}
```

Предыдущий пример распечатает `2`. Стратегия округления нечувствительна к регистру, поэтому можно написать как `'CEIL'`, так и `'ceil'`. Если второй аргумент не указан, число округляется до ближайшего целого.

## Операции над строками

### `number_format`

Функция `number_format` позволяет форматировать указанное число с указанными символами для разделителей группы разрядов и дробной части, а также с указанным количеством дробных цифр. Эта функция ожидает как минимум один аргумент и до четырех. Список аргументов в том порядке, как они ожидаются функцией:

1. Число для форматирования;
2. Количество дробных цифр \(опционально\);
3. Разделитель дробной части \(опционально\);
4. Разделитель группы разрядов \(опционально\);

```csharp
{{ number_format(11000.136, 2, '.', ' ') }}
```

Предыдущий пример распечатает `11 000.14`.

### `capitalize`

Эта функция капитализации строки ожидает один аргумент. В результате выполнения функции первое слово строки станет с заглавной буквы.

```csharp
{{ capitalize('hello world') }}
```

Предыдущий пример распечатает `Hello world`.

### `format`

Данная функция принимает строку-шаблон, форматируя её с помощью переданных последующих аргументов. Здесь используется метод `String.format`, доступный в Java. Более подробно о форматировании строк можно почитать в [интернете](https://dzone.com/articles/java-string-format-examples).

```csharp
{{ format('hello %s! %d', 'world', 123) }}
```

Предыдущий пример распечатает `hello world! 123`.

### `lower`

Преобразует переданную строку в нижний регистр.

```csharp
{{ lower('JUNIPERBOT') }}
```

Предыдущий пример распечатает `juniperbot`.

### `upper`

Преобразует переданную строку в верхний регистр.

```csharp
{{ upper('juniperbot') }}
```

Предыдущий пример распечатает `JUNIPERBOT`.

### `replace`

Данная функция принимает на вход строку и карту, заменяя в строке все вхождения ключей карты на соответствующие им значения.

```csharp
{{ replace('Hello %name%', { '%name%': 'world' }) }}
```

Предыдущий пример распечатает `Hello world`.

















#### `batch`

The batch function splits a given list in equally sized groups of items. It expects two or three arguments. A list as first argument, note that a list in Jtwig is a configurable concept as mentioned previously, whereby the `CollectionConverter` defined in the configuration will be used, it depends on the converter defined in the environment. The second argument is the group size. There is also an optional third argument used as padding, that is, if the last group is incomplete, the third argument will be used to fill it.

```text
{{ batch([1,2,3], 2) }}
```

The previous example will output `[[1, 2], [3]]`.

```text
{{ batch([1,2,3], 2, 0) }}
```

The previous example, now with the padding argument, will output `[[1, 2], [3, 0]]`.

#### `block`

Block function can be used to output the content of a defined block tag \(check [block tag definition](http://jtwig.org/documentation/reference/tags/modular/block)\).

```text
{% block one %}Hello{% block %}{{ block('one') }}
```

The previous example will print `HelloHello`.

#### \`\`

#### `concat` or `concatenate`

This function allows one to concatenate a set of strings. It is expecting an arbitrary number of arguments \(varargs\).

```text
{{ concat('1', '+', '1', '=', '2') }}
```

Under the wood it uses the defined `StringConverter` to convert individual objects to a string representation and then concatenating them. The previous example will output `1+1=2`.

#### `constant`

The constant function comes with two possible outputs depending on the number of arguments supplied. If one argument is supplied, it will return the value of the constant. If two arguments are provided, then it will compare the constant value against the second argument.

```text
{{ constant("org.jtwig.example.TestClass.CONSTANT_NAME") }}
```

As shown in the above example, the expression will print the result of evaluating \(using reflection\) the constant with name `CONSTANT_NAME` defined in class `org.jtwig.example.TestClass`. Note that the evaluation will only work if the constant is public.

```text
{{ constant("org.jtwig.example.TestClass.CONSTANT_NAME", "value") }}
```

The above example will return a Boolean expression. It will be `true` if the constant value is equal to `"value"`.

#### `default`

The default function is expecting two arguments. It returns the second argument if the first argument is either `null` or `Undefined`.

```text
{{ default(null, 'Hello') }} {{ default(undefinedVariable, 'World') }}
```

if variable `undefinedVariable` is not defined in the provided `JtwigModel` then the previous example will produce `Hello World`.

#### `first`

The first function returns the first element of a collection or String. If the argument provided is not a collection or a String, it will just return the input argument.

```text
{{ first([1, 2]) }}
```

If the given argument is an empty list or String, then it returns `Undefined`. Note that this function uses the `CollectionConverter` mechanism. The previous template will output `1`.

\`\`

#### `join`

The `join` function provides functionality somehow similar to the `concat` function, however they have some differences. To start with, `join` takes only one or two arguments, where the first argument is expected to be a list and the second, optional, argument a string to be used as the separator.

```text
{{ join([1, null, 2], ', ') }}
```

The previous example will print `1, 2`. Note that, `join` function ignores `null` values.

#### `keys`

Keys function can be used to expose the collection of keys for a given collection. It uses the configured `CollectionConverter` \(for more details check the Environment documentation\).

```text
{{ keys(['A', 'B']) }}
```

The previous example, as per the default configuration, will print `[1, 2]`.

#### `last`

The last function returns the last element of a collection or String. If the argument provided is not a collection or a String, it will just return the input argument.

```text
{{ last([1, 2]) }}
```

If the given argument is an empty list or String, then it returns `Undefined`. Note that this function uses the `CollectionConverter` mechanism \(check `Environment` documentation for more information\). The previous template will output `2`.

#### `length`

The length function returns the length of a given collection or String. If neither a collection or String is provided then it returns `0` for both `null` and `Undefined`, otherwise `1` will be the result.

```text
{{ length([1, 2]) }}
```

```text
{{ length(null) }}
```

```text
{{ length(9) }}
```

The previous examples will print respectively `2`, `0` and `1`. Note that this function uses the defined `CollectionConverter` configured, for more information visit the `Environment` documentation.

#### \`\`

#### `merge`

The `merge` function allows one to merge an arbitrary number of lists together by the given order. This function requires at least two arguments to run. It also supports singular elements as arguments.

```text
{{ merge(1, 2, 3) }}
```

```text
{{ merge([1, 2], 3) }}
```

The previous two examples return the same output, which is, `[1, 2, 3]`. Note that, this function uses the `CollectionConverter` defined by the Jtwig configuration.

#### \`\`

#### `reverse`

Reverse function reverses the order of the elements in a given collection or String. If no collection neither String is provided then it returns the given argument.

```text
{{ reverse([1, 2]) }}
```

The previous example will print `[2, 1]`. Note that this function uses the defined `CollectionConverter` configured, for more information visit the `Environment` documentation.

#### \`\`

#### `slice`

This function is expecting three arguments, where the first argument can either be a String or a collection \(it uses `CollectionConverter` under the wood\), and an integer as second and third arguments.

```text
{{ slice("123", 1, 1) }}
```

```text
{{ slice([1, 2, 3], 0, 2) }}
```

The second argument is the index position the slice will start from \(inclusive\), where the third argument is the length of the slice. As shown in the previous two examples, the result will be `"2"` and `[1, 2]` respectively. Note that, slice is smart enough to handle boudary cases, for exaple:

```text
{{ slice("123", 2, 3) }}
```

```text
{{ slice("123", 5, 1) }}
```

The previous examples will still return a slice, depending on the number of characters or items provided in the first argument, the previous examples would then resolve the slice to `"3"` and `""`.

#### `sort`

Sort can be used to sort elements of a given collection in ascending order. It is based on the underlying core Java `java.lang.Comparable` interface, which elements should implement.

```text
{{ sort([1, 3, 2]) }}
```

The previous example will produce `[1, 2, 3]`.

#### `split`

This function expects two arguments, using the second argument provided to split the first one into a collection. Such arguments are converted to String using the `StringConverter` configured in the `Environment` as detailed previously.

```text
{{ split('jtwig-2', '-') }}
```

The previous example will return `[jtwig, 2]`.

#### \`\`

#### `title`

The title function is expecting one String argument, capitalizing the first letter of all words present in it.

```text
{{ title('hello world') }}
```

The previous example will produce `Hello World`. Note that this function uses `StringConverter` to convert the arguments to a String, check `Environment` documentation for further information.

#### `trim`

Similar to the Java sibling `String::trim`, the trim function in Jtwig removes any whitespace characters from the beginning and/or ending of the given argument.

```text
{{ trim('  Hello World  ') }}
```

The previous example will produce `Hello World`. Note that this function uses `StringConverter` to convert the arguments to a String, check `Environment` documentation for further information.

#### \`\`

#### \`\`

