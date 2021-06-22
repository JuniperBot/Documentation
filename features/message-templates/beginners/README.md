---
description: Message Templates "For Dummies".
---

# Beginners

![](../../../.gitbook/assets/image%20%2823%29.png)

This article is dedicated to those who do not want learn all the possibilities of message templates deeply, but just want to understand how to use the basic variables in templates and what variables exist.

### Inserting Variables

Variables are inserted using double curly braces inside the template in the place you need, for example:

```text
Hello, {{ member }}! Welcome to our server!
```

In the example above, the `member` variable is inserted in the template and denoted by double curly braces. This means that `{{ member }}` will be replaced with a mention of the member, that is, the following will be printed in the channel:

```text
Hello, @Member! Welcome to our server!
```

Easy peasy.

### What variables we have? <a id="list"></a>

All existing variables are described in the [Variables](variables.md) article. Take the variable you are interested in and just paste it in the right place in your template.

