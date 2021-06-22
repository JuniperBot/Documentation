---
description: Data Types convertation
---

# Type Convert

In some places where a certain data type is required as an argument to a tag or function, the Template Engine will try to automatically convert input data to the data type required.

{% hint style="warning" %}
Type Convert works only works for global [functions](../functions.md) for now. Functions in complex [data types](../types.md) requires strictly defined argument types. In the future, perhaps this will be improved.
{% endhint %}

### Numbers <a id="numbers"></a>

| Source | Number Representative |
| :--- | :--- |
| Null Reference \(`null`\) | 0 |
| Undefined | 0 |
| Boolean | 1 for `true`, 0 for `false` |
| String | Will try to parse the number in the string |

‌

### Boolean <a id="boolean"></a>

| Source | Boolean Representative |
| :--- | :--- |
| Null Reference \(`null`\) | `false` |
| Undefined | `false` |
| String | `false` if empty, `true` otherwise |
| List or Map | `false` if empty, `true` otherwise |
| Number | `false` for 0, `true` otherwise |

