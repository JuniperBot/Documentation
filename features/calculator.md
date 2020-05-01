---
description: JuniperBot Calculator Description
---

# Calculator

Calculator in JuniperBot is presented as "math" command. This article shows what it can do.

### Mathematical Operators

| Operator | Description |
| :--- | :--- |
| + | Additive operator / Unary plus |
| - | Subtraction operator / Unary minus |
| \* | Multiplication operator, can be omitted in front of an open bracket |
| / | Division operator |
| % | Remainder operator \(Modulo\) |
| ^ | Power operator |

### Boolean Operators

| Operator | Description |
| :--- | :--- |
| = | Equals |
| == | Equals |
| != | Not equals |
| &lt;&gt; | Not equals |
| &lt; | Less than |
| &lt;= | Less than or equal to |
| &gt; | Greater than |
| &gt;= | Greater than or equal to |
| && | Boolean "AND" |
| \|\| | Boolean "OR" |

{% hint style="info" %}
Boolean operators result always in a BigDecimal value of 1 or 0 \(zero\). Any non-zero value is treated as a _true_ value.
{% endhint %}

### Supported Functions

| Function | Description |
| :--- | :--- |
| `NOT(expression)` | Boolean negation, 1 \(means true\) if the expression is not zero |
| `IF(condition, value_if_true, value_if_false)` | Returns one value if the condition evaluates to true or the other if it evaluates to false |
| `RANDOM()` | Produces a random number between 0 and 1 |
| `MIN(e1, e2, ...)` | Returns the smallest of the given expressions |
| `MAX(e1, e2, ...)` | Returns the biggest of the given expressions |
| `ABS(expression)` | Returns the absolute \(non-negative\) value of the expression |
| `ROUND(expression, precision)` | Rounds a value to a certain number of digits, uses the current rounding mode |
| `FLOOR(expression)` | Rounds the value down to the nearest integer |
| `CEILING(expression)` | Rounds the value up to the nearest integer |
| `LOG(expression)` | Returns the natural logarithm \(base e\) of an expression |
| `LOG10(expression)` | Returns the common logarithm \(base 10\) of an expression |
| `SQRT(expression)` | Returns the square root of an expression |
| `SIN(expression)` | Returns the trigonometric sine of an angle \(in degrees\) |
| `COS(expression)` | Returns the trigonometric cosine of an angle \(in degrees\) |
| `TAN(expression)` | Returns the trigonometric tangens of an angle \(in degrees\) |
| `COT(expression)` | Returns the trigonometric cotangens of an angle \(in degrees\) |
| `SEC(expression)` | Returns the secant \(in degrees\) |
| `CSC(expression)` | Returns the cosecant \(in degrees\) |
| `ASIN(expression)` | Returns the angle of asin \(in degrees\) |
| `ACOS(expression)` | Returns the angle of acos \(in degrees\) |
| `ATAN(expression)` | Returns the angle of atan \(in degrees\) |
| `ACOT(expression)` | Returns the angle of acot \(in degrees\) |
| `ATAN2(y,x)` | Returns the angle of atan2 \(in degrees\) |
| `SINH(expression)` | Returns the hyperbolic sine of a value |
| `COSH(expression)` | Returns the hyperbolic cosine of a value |
| `TANH(expression)` | Returns the hyperbolic tangens of a value |
| `COTH(expression)` | Returns the hyperbolic cotangens of a value |
| `SECH(expression)` | Returns the hyperbolic secant \(in degrees\) |
| `CSCH(expression)` | Returns the hyperbolic cosecant \(in degrees\) |
| `ASINH(expression)` | Returns the angle of hyperbolic sine \(in degrees\) |
| `ACOSH(expression)` | Returns the angle of hyperbolic cosine \(in degrees\) |
| `ATANH(expression)` | Returns the angle of hyperbolic tangens of a value |
| `RAD(expression)` | Converts an angle measured in degrees to an approximately equivalent angle measured in radians |
| `DEG(expression)` | Converts an angle measured in radians to an approximately equivalent angle measured in degrees |
| `FACT(expression)` | Retuns the factorial value of an integer. Will return 1 for 0 or a negative number |

### Supported Constants

| Constant | Description |
| :--- | :--- |
| `e` | The value of e, exact to 70 digits |
| `PI` | The value of PI, exact to 100 digits |
| `TRUE` | The value one |
| `FALSE` | The value zero |
| `NULL` | The null value |

