---
description: Template Engine Tags
---

# Tags

Tags are a set of various built-in constructs and operations over a template. They are declared using [code islands](syntax/code-islands.md) and defines the behavior of the template.

## Commands <a id="commands"></a>

Command constructs allows one to run specific commands against template. An important aspect common to all commands is that they never produce content, they only produce side effects.

### `set`

 The `set` command allows to specify an assignment operation inside a template, it will assign to the result of an expression to the specified variable:

```csharp
{% set five = 2 + 3 %}
```

In the previous example we assigned the result of evaluating the expression `2 + 3` to the variable `five`.

Note again that the output of the previous example will be empty because, as mentioned before, `set` as a command, does not produce content, it just affects the context defining, or redefining a variable.

### `global`

The `global` command is the same as `set` but it will assign the result of evaluating the expression in global context. It means the global variable will be available in next template values of message template. For example, a global variable defined in Message Content Template will be also available in Embed Content Template.

```csharp
{% global six = 3 + 3 %}
```

In the previous example we assigned the result of evaluating the expression `3 + 3` to the variable `six` and will be available globally.

### `do`

The `do` command just evaluates a given expression.

```csharp
{% do something.run() %}
```

There is not a lot to say about this construct, it might be usefull to trigger behaviour from the template by running an object function.

### `return`

The `return` command will interrupt template evaluation with an error returned to the user.

```csharp
{% return 'Some error just happened!' %}
```

You can pass an [Embed]() instead of string \(but keep in mind that you shouldn't send it using its `send` function\).

### `require`

The `require` is an extension for `return` command:

```csharp
{% require выражение returning 'Some error just happened!' %}
```

This command will only return an error if result of evaluating the expression is `false` according the `Type Convert`.

You can pass an [Embed]() instead of string \(but keep in mind that you shouldn't send it using its `send` function\).

### `use`

The `use` command enables additional template behaviour. 

#### strict

Enables template evaluation in strict mode. This means that the Template Engine will return a compilation error in the following cases:

* Attempt to output an undefined variable;
* Attempt to access a non-existent property of an object;
* An attempt to call a non-existent object function or with incorrectly passed arguments.

You can enable this behaviour the following way:

```csharp
{% use 'strict' %}
```

## Control Flow <a id="control"></a>

Template Engine implements basic control flow constructs such as `if` conditions and `for` loops.

### Conditions — `if/elseif/else`  <a id="if"></a>

`If` conditions are the simplest control flow in Template Engine. It supports consecutive `elseif` conditions and the common `else` construct too.

```csharp
{% if (expression) %}
... content if expression is evaluated to true ...
{% elseif (anotherExpression) %}
... content if anotherExpression is evaluated to true ...
{% else %}
... content if none of the previous conditions are met ...
{% endif %}
```

Note that `if` constructs will only output the content of the first block which condition is evaluated to `true` according to [Type Convert](syntax/type-convert.md).

In terms of variable scoping, `if` inner content shares the context with the parent context, this means `if` conditions can affect variables in the outer scope.

```csharp
{% set variable = "a" %}
{% if (true) %}
    {% set variable = "b" %}
{% endif %}
{{ variable }}
```

The previous example will output `b` which illustrates how scoping works on if conditions by sharing the context with the parent construct.

```csharp
{% if (1 != 2) %}
    {% return '1 is not 2. Oh wow!' %}
{% endif %}
This text will not be printed because the error.
```

The previous example will conditionally returns an error.

### Loops — `for`  <a id="loops"></a>

Template Engine allows to iterate over a list or a map.

```csharp
{# Example with list #}
{% for item in list %}
... content using variable item ...
{% endfor %}

{# Example with map #}
{% for key, value in map %}
... content using variables key and value ...
{% endfor %}
```

#### `loop` variable

`for` loops come with an extra variable defined in the context, the `loop` variable. The loop variable provides a set of useful properties when within a for loop, check below the properties exposed by this variable:

| Property | Description |
| :--- | :--- |
| `length` | Size of the list or map being iterated |
| `index` | Current iteration count starting in 1 |
| `index0` | Current iteration count starting in 0 |
| `revindex` | Remaining number of iterations to reach the end of the list or map, ends in 1 |
| `revindex0` | Remaining number of iterations to reach the end of the list or map, ends in 0 |
| `first` | Boolean property only `true` in the first iteration |
| `last` | Boolean property only `true` in the last iteration |
| `parent` | Accessing the parent context |

```csharp
{% for item in [1, 2, 3] %}
    {% if (loop.first) %}
        Start
    {% endif %}
{% endfor %}
```

The previous example will output `Start` only once.

This `loop` variable is only bound to the `for` context, it means this variable will not be visible outside of the for loop scope. If there is a `loop` variable in the context, it will not be overriden but to access it one need to get the parent context, for example:

```csharp
{% set loop = 1 %}
{% for item in [1, 2, 3] %}
    {% if (loop.first) %}
        {{ loop.parent.loop }}
        {% set loop = 2 %}
    {% endif %}
{% endfor %}
{{ loop }}
```

The previous template will print `1 2`. Note that setting `loop` inside the for loop will write to the context, but won't override the for loop bound variable. The value `loop` variable defined inside the loop is then available outside of the loop scope.

## Other <a id="other"></a>

### `filter`

The `filter` construct is the way apply [functions](functions.md) the a given content. It uses the provided body as the first argument in the specified function.

```csharp
{% filter lower | capitalize -%}
HELLO WORLD
{%- endfilter %}
```

The previous example will produce `Hello world`. As we can see, the filter specified results in the composition of two distinct functions, it will first apply the `lower` function to the content HELLO WORLD, producing `hello world` and then apply the `capitalize` function producing `Hello world`.

### `verbatim`

The `verbatim` tag is usefull avoiding the specifics around Template Engine syntax, as it will not try to parse the content.

```csharp
{% verbatim %}
{{ test }}
{% endverbatim %}
```

 The output of the previous template will be `{{ test }}`.

