---
description: Code Islands of Template Engine
---

# Code Islands

In its simplest form, a template is a text that will be sent as message as is.

However, the whole point of the template engine is the ability to format this text in a given way, use control structures \(conditions or loops\) inside it, and even perform some actions. The "code islands" are used to do that.

### Code <a id="code"></a>

Code islands begin with `{%` and ends with `%}`, just as simple as that. [Tags](../tags.md) are used inside code constructs to implement a control structures \(conditions or loops\), declare variables and much more.

```java
{% tag %}
```

Each code construct can perform only single operation or declare part of a control structure.

The logical sequence is formed by using many separate islands of code for each individual operation or part of the control structure.

### Whitespace Control <a id="whitespace"></a>

Tied up with the code island syntax is another syntactical enabled feature, the white space control functionality. This allows one to remove white spaces before or after a code island. In order to accomplish that, append/prepend the symbol `-` to the beginning/ending of the code island. Let's take for example:

```c
{% if (1 == 1) -%}     text     {%- endif %}
```

 Such code will produce `text` without white spaces.

### Output <a id="expressions"></a>

In JuniperBot Template Engine there is only one way to write the value of variable or an expression to the output. That is accomplished with the print operation as shown below:

```c
{{ expression }}
```

Note that output also support the white space control feature, using the same approach as per code islands:

```c
{{- expression -}}
```

### Comments <a id="comments"></a>

In template engine you can add comments that will not be printed anywhere:

```scheme
{# This is the content of the comment.
And it can be a multi-line content. #}
```

Again, comment constructs also support white space control feature in the same way as code islands:

```text
{#- Your awesome comment -#}
```

