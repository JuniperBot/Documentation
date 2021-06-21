---
description: Member's Ranking EXP description
---

# Experience

## Text Comminucation <a id="text"></a>

Each time member sends message in text channel he will gain random amount of EXP from 15 to 25\* once per minute. "rank" command can be used to check the progress.

{% hint style="info" %}
15 - 25 is the default range in case if 100% multiplier is the active in ranking settings of [server's dashboard](../../#configure). It will follow this multiplier.
{% endhint %}

## Voice Communication <a id="voice"></a>

{% hint style="success" %}
Voice EXP is only available to users [supported us](https://juniper.bot/donate)!
{% endhint %}

Voice EXP and Voice Activity is calculated only for active users who:

* Have the microphone active and is not muted;
* Have the sound enabled and is not deafen;
* Not bots.

Voice EXP per minute in ideal conditions is calculed using following formula:

$$
exp = 6 * count * multiplier
$$

* _count_ - amount of active users in voice channel;
* _multiplier_ - EXP multiplier configured in [server's dashboard](../../#configure) \(100% = 1, 200% = 2 and so on\).

{% hint style="info" %}
You can \(and should!\) specify the maxumim _count_ value so members will not gain an extremely high EXP amounts in case if a lot of people in the voice channel currently. You can configure it in Member Ranking section of [server's dashboard](../../#configure).
{% endhint %}

You should keep in mind following things regarding voice EXP and voice activity:

1. EXP and activity is given to active members only if at least two of them currently active in the voice channel;
2. EXP is cumulative.  It means that if three members are active currently, they will gain **x3 EXP** while they are active.  If one of them left the channel, mutes himself or deafen, he is not active anymore so from this moment the others two will gain **x2 EXP** but they still got all the exp while the third was active.  If second left the channel, muted/deafen too, the last one will not gain any EXP anymore but still got the EXP he gained before the others became inactive.

{% hint style="info" %}
One minute of talking is not a required minimum. EXP will be given for less time ranges as well, proportionally.

In the other words, 30 seconds of communication members will gain them the half of the EXP they could get for the whole minute according to the formula above.
{% endhint %}

{% hint style="warning" %}
**Important!** Note that already accumulated EXP and voice activity will be applied to the rank only after current voice session end if member left the voice channel or changed it.

There will not be any visual change in the ranking while member still in the channel continiously. 
{% endhint %}

## Levels <a id="levels"></a>

Experience for each level is calculated using this formula:

$$
exp = 5 * level^2 + 50 * level + 100
$$

{% hint style="info" %}
Maximum possible level is 999
{% endhint %}

Thus, for the hundred levels the experience table with the approximate time of continuous communication necessary to obtain this level will look like this:

| Level | EXP until next | Required EXP | Time until next \(minutes\) |
| :--- | :--- | :--- | :--- |
| 0 | 100 | 0 | 4 - 7 |
| 1 | 55 | 100 | 3 - 4 |
| 2 | 65 | 155 | 3 - 5 |
| 3 | 75 | 220 | 3 - 5 |
| 4 | 85 | 295 | 4 - 6 |
| 5 | 95 | 380 | 4 - 7 |
| 6 | 105 | 475 | 5 - 7 |
| 7 | 115 | 580 | 5 - 8 |
| 8 | 125 | 695 | 5 - 9 |
| 9 | 135 | 820 | 6 - 9 |
| 10 | 145 | 955 | 6 - 10 |
| 11 | 155 | 1100 | 7 - 11 |
| 12 | 165 | 1255 | 7 - 11 |
| 13 | 175 | 1420 | 7 - 12 |
| 14 | 185 | 1595 | 8 - 13 |
| 15 | 195 | 1780 | 8 - 13 |
| 16 | 205 | 1975 | 9 - 14 |
| 17 | 215 | 2180 | 9 - 15 |
| 18 | 225 | 2395 | 9 - 15 |
| 19 | 235 | 2620 | 10 - 16 |
| 20 | 245 | 2855 | 10 - 17 |
| 21 | 255 | 3100 | 11 - 17 |
| 22 | 265 | 3355 | 11 - 18 |
| 23 | 275 | 3620 | 11 - 19 |
| 24 | 285 | 3895 | 12 - 19 |
| 25 | 295 | 4180 | 12 - 20 |
| 26 | 305 | 4475 | 13 - 21 |
| 27 | 315 | 4780 | 13 - 21 |
| 28 | 325 | 5095 | 13 - 22 |
| 29 | 335 | 5420 | 14 - 23 |
| 30 | 345 | 5755 | 14 - 23 |
| 31 | 355 | 6100 | 15 - 24 |
| 32 | 365 | 6455 | 15 - 25 |
| 33 | 375 | 6820 | 15 - 25 |
| 34 | 385 | 7195 | 16 - 26 |
| 35 | 395 | 7580 | 16 - 27 |
| 36 | 405 | 7975 | 17 - 27 |
| 37 | 415 | 8380 | 17 - 28 |
| 38 | 425 | 8795 | 17 - 29 |
| 39 | 435 | 9220 | 18 - 29 |
| 40 | 445 | 9655 | 18 - 30 |
| 41 | 455 | 10100 | 19 - 31 |
| 42 | 465 | 10555 | 19 - 31 |
| 43 | 475 | 11020 | 19 - 32 |
| 44 | 485 | 11495 | 20 - 33 |
| 45 | 495 | 11980 | 20 - 33 |
| 46 | 505 | 12475 | 21 - 34 |
| 47 | 515 | 12980 | 21 - 35 |
| 48 | 525 | 13495 | 21 - 35 |
| 49 | 535 | 14020 | 22 - 36 |
| 50 | 545 | 14555 | 22 - 37 |
| 51 | 555 | 15100 | 23 - 37 |
| 52 | 565 | 15655 | 23 - 38 |
| 53 | 575 | 16220 | 23 - 39 |
| 54 | 585 | 16795 | 24 - 39 |
| 55 | 595 | 17380 | 24 - 40 |
| 56 | 605 | 17975 | 25 - 41 |
| 57 | 615 | 18580 | 25 - 41 |
| 58 | 625 | 19195 | 25 - 42 |
| 59 | 635 | 19820 | 26 - 43 |
| 60 | 645 | 20455 | 26 - 43 |
| 61 | 655 | 21100 | 27 - 44 |
| 62 | 665 | 21755 | 27 - 45 |
| 63 | 675 | 22420 | 27 - 45 |
| 64 | 685 | 23095 | 28 - 46 |
| 65 | 695 | 23780 | 28 - 47 |
| 66 | 705 | 24475 | 29 - 47 |
| 67 | 715 | 25180 | 29 - 48 |
| 68 | 725 | 25895 | 29 - 49 |
| 69 | 735 | 26620 | 30 - 49 |
| 70 | 745 | 27355 | 30 - 50 |
| 71 | 755 | 28100 | 31 - 51 |
| 72 | 765 | 28855 | 31 - 51 |
| 73 | 775 | 29620 | 31 - 52 |
| 74 | 785 | 30395 | 32 - 53 |
| 75 | 795 | 31180 | 32 - 53 |
| 76 | 805 | 31975 | 33 - 54 |
| 77 | 815 | 32780 | 33 - 55 |
| 78 | 825 | 33595 | 33 - 55 |
| 79 | 835 | 34420 | 34 - 56 |
| 80 | 845 | 35255 | 34 - 57 |
| 81 | 855 | 36100 | 35 - 57 |
| 82 | 865 | 36955 | 35 - 58 |
| 83 | 875 | 37820 | 35 - 59 |
| 84 | 885 | 38695 | 36 - 59 |
| 85 | 895 | 39580 | 36 - 60 |
| 86 | 905 | 40475 | 37 - 61 |
| 87 | 915 | 41380 | 37 - 61 |
| 88 | 925 | 42295 | 37 - 62 |
| 89 | 935 | 43220 | 38 - 63 |
| 90 | 945 | 44155 | 38 - 63 |
| 91 | 955 | 45100 | 39 - 64 |
| 92 | 965 | 46055 | 39 - 65 |
| 93 | 975 | 47020 | 39 - 65 |
| 94 | 985 | 47995 | 40 - 66 |
| 95 | 995 | 48980 | 40 - 67 |
| 96 | 1005 | 49975 | 41 - 67 |
| 97 | 1015 | 50980 | 41 - 68 |
| 98 | 1025 | 51995 | 41 - 69 |
| 99 | 1035 | 53020 | 42 - 69 |
| 100 | 1045 | 54055 | 42 - 70 |

