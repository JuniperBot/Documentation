# Data Types

## Template variables data types

Some template variables can be extended and provide more additional information.

For example, we have `{server.createdAt}` variable marked as [DateTime ](data-types.md#datetime)type. You can extend this variable to get only time or only date of server creation. To do so you should look at corresponding list of supported properties, find property for time or date and append it to desired variable \(eg. replace the `*` with your variable name\).

So, if you want to get only server creation date, you must use the `{server.createdAt.shortDate}` variable.

### Member, Server, Channel

They are already described as [Member](template-variables.md#member), [Server ](template-variables.md#server)and [Channel ](template-variables.md#channel)variable sets, just replace their root keys with corresponding property name.

### DateTime

| Property | Description | Example |
| :--- | :--- | :--- |
| `{*}` | Root value as medium date and time | May 7, 2017, 10:48:55 PM |
| `{*.shortTime}` | Short time | 10:48 PM |
| `{*.mediumTime}` | Medium time | 10:48:55 PM |
| `{*.longTime}` | Long time | 10:48:55 PM SAMT |
| `{*.fullTime}` | Full time | 10:48:55 PM Samara Standard Time |
| `{*.shortDate}` | Short date | 5/7/17 |
| `{*.mediumDate}` | Medium date | May 7, 2017 |
| `{*.fullDate}` | Full date | Sunday, May 7, 2017 |
| `{*.shortDateTime}` | Short date and time | 5/7/17, 10:48 PM |
| `{*.mediumDateTime}` | Medium date and time | May 7, 2017, 10:48:55 PM |
| `{*.longDateTime}` | Long date and time | May 7, 2017 at 10:48:55 PM SAMT |
| `{*.fullDateTime}` | Full date and time | Sunday, May 7, 2017 at 10:48:55 PM Samara Standard Time |

## Command arguments

### Durations

Used in commands with specified duration of some action. Written in format of amounts and units without spaces, for example:

* 1day
* 1hour
* 8hours30mins

Below is table of all supported units, their names and short names:

| Unit | Name |
| :--- | :--- |
| Year | `y`, `year`, `years`, `г`, `год`, `года`, `лет` |
| Months | `mo`, `mos`, `month`, `months`, `мес`, `месяц`, `месяца`, `месяцев` |
| Weeks | `w`, `week`, `weeks`, `н`, `нед`, `неделя`, `недели`, `недель`, `неделю` |
| Days | `d`, `day`, `days`, `д`, `день`, `дня`, `дней` |
| Hours | `h`, `hour`, `hours`, `ч`, `час`, `часа`, `часов` |
| Minutes | `min`, `mins`, `minute`, `minutes`, `мин`, `минута`, `минуту`, `минуты`, `минут` |
| Seconds | `s`, `sec`, `secs`, `second`, `seconds`, `c`, `сек`, `секунда`, `секунду`, `секунды`, `секунд` |

