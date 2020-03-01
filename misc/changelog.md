---
description: The latest JuniperBot changes are described here.
---

# Changelog

### Version 8.3

* Auto-moderation improvements:
  * Fixed an issue with flood detection not worked properly;
* Some small fixes and improvements.

### Version 8.2

* **\[Donate\]** Rank card customization:
  * Configure colors of background, fonts, level progress line, shadows;
  * Upload your own background image;
* New template variable `{message.mentions}` you can use to get message mentions info:
  * Amount of mentioned members in message: `{message.mentions}`;
  * Get mentioned member by his number of occurrence in message `{message.mentions.1}`;
* Auto-moderation improvements:
  * Fixed an issue when sending pictures was triggered by flood filter;
  * Ban and kick in filter restraints;
* Fixed an issues with link parsers for vk.com;
* Fixed an issue when member lost access to channel with direct permission configured for him if he was unmuted there;
* Discord's audit ban reason now contains moderator banned him;
* Some small fixes and improvements.

### Version 8.1

* Auto-moderation fixes and improvements:
  * Fixed an issue when bad words filter not worked correctly for compound words \(fox, foxy, foxes\);
  * **\[web\]** Minimal message length option in caps filter has been replaced with minimum amount of letters;
  * **\[web\]** New flood filter options:
    * Optional sequential messages counting \(if disabled, it will count all nearest messages\);
    * Ability to stop flood counter reset when a violation is detected;
  * The flood filter is not case sensitive now;
* Some small fixes and improvements.

### Version 8.0-hotfix

* Server owner and administrators can now remove their own warns using `снятьпред/remwarn` command;
* Auto-moderation fixes and improvements:
  * Fixed an issue with bad words wasn't case-independent;
  * Fixed an issue with capslock triggered on messaged without any letter;
  * Fixed an issue with capslock triggered on emote's and mention's names;
  * Messages deleted by auto-moderation now logging at audit with auto-moderation related reason;
  * **\[web\]** Infraction notification message deletion can be configured or disabled at all in filter settings;
  * Capslock filter now has length 10 characters и 70% capslock by default;
* Some small fixes and improvements.

### Version 8.0

* **\[Moderation\]** Huge moderation improvements:
  * Auto-moderation system watching for:
    * External links and server invites;
    * Bad words;
    * Repeated text \(flood\);
    * Сaps Lock;
    * Excessive use of emoticons;
    * Excessive use of mentions;
  * Actions per infractions improvements:
    * New duration selection interface;
    * Bans duration, not just mute as before;
* **\[Audio\]** Most of the informational messages will be deleted after some time to keep channel clean;
* **\[web\]** New emoji selector:
  * Custom command reactions select;
  * Emoji insert button in all message templates;
* Changing roles custom commands now can be used to @mentioned members \(optional\);
* Some small fixes and improvements.

### Version 7.13

* `!help` and `!bonus` commands now are language independent;
* Fixed track listened status on repeat mode;
* Fixed broken `!cat/!кот` command;
* **\[web\]** The set of emojis was updated \(reactions selection\);
* Some small fixes and improvements.

### Version 7.12

* Fixed broken Twitch.tv subscriptions;
* Fixed an issue when you was able to view the bot's rank;
* Fixed an issue when playing track can stuck at the end of playback;
* Fixed message ID formatting at audit logs;
* New template variables:
  * `{message.*}` - [message information variables set](https://docs.juniper.bot/misc/template-variables#message)usable for:
    * Ranking as source message gained new level;
    * Custom commands as source message invoked these commands;
  * `{currentTime}` - current time in guild's timezone;
* Some small fixes and improvements.

### Version 7.11

* Music feature improvements:
  * **\[web\]** New option to select search source:
    * Yandex.Music \(by default\);
    * YouTube;
    * SoundCloud;
  * Music control icons have been updated;
  * Preparing infrastructure to recover stable YouTube playback;
* **\[Audit\]** Fixed message edit audit action broken link in Russian locale;
* Fixed unmute issue of temporary mutes;
* `!serverinfo/!сервер` channel icons have been updated;
* Some small fixes and improvements.

### Version 7.10

* Many optimizations and performance improvements;
* **\[web\]** Custom commands improvements:
  * New compact custom commands settings;
  * New command settings dialog for both custom and internal commands;
* **\[Audit\]** Fixed layout issues with audit forwarding messages;
* Some small fixes and improvements.

### Version 7.9

* Improved bot statistics notifications to bot lists;
* Patreon `юзер/user` was updated;
* Fixed warning expiration;
* Fixed reserved commands checks in custom commands;
* Fixed dashboard performance issues \(lags on weak devices\);
* Some small fixes and improvements.

### Version 7.8

* Total commands handled counter is back;
* Custom status support in `юзер/user`;
* `юзер/user` command now contains badges. For now they are only for developer and Patrons;
* Some small fixes and improvements.

### Version 7.7

* Internal infrastructure was update to improve performance and stability \(yeah we hope so\);
* **\[Рейтинг\]** Ranking system improvements:
  * `лидеры/leaders` command now shows Top-10 of members on the server;
  * Fixed `ранг/rank` didn't worker for some members;
* **\[web\]** New shard statistics;
* Some small fixes and improvements.

### Version 7.6

* **\[Audit\]** New action type for voice move event;
* Fixed custom commands invocations via @mention;
* `вычислить/math` command improvements:
  * Precision is 32 digits now;
  * Fixed error handling;
* Fixed duration texts for mute commands, again;
* Fixed role granting conflict using voice channels \(between In-Voice role and ranking reward\);
* Mute role now configures category permissions according to text channel;
* Custom command template variable `{content}` now supports parameters by their sequence number \(divided by space\): `{content:1}`, `{content:2}` and so on;
* Some small fixes and improvements.

### Version 7.5

* **\[Audit\]** Fixed name changing logging;
* **\[Ranking\]** Ranking system improvements:
  * Command `ранг/rank` now works with user IDs;
  * Ranking card will not show cookies if they weren't enabled;
  * Fixed issue when members gained EXP using voice even if they had EXP ignoring role;
  * Added an option to set maximum member count in voice channel increasing voice EXP;
* DM notifications about bans and warnings now contains their expiration dates;
* "Assistant" was disabled as unnecessary and unwilling to support it;
* New command `вычислить/math` for mathematical expressions evaluation;
* Fixed nickname restore on member rejoin;
* Fixed duration texts for mute commands, again;
* Fixed audit warning action not contained warning expiration if specified;
* Fixed command `очистить/clear` usage with @mentioned member;
* Some small fixes and improvements.

### Version 7.4

* **\[Ranking\]** Ranking system improvements:
  * **\[Patreon\]** Exp multiplier in range 50% - 500%
  * **\[Patreon\]** Voice experience gaining \(with multiplier support too\);
  * Command `ранг/rank` now uses image cards;
* **\[music\]** Music improvements:
  * **\[Patreon\]** Playback progress bar;
  * `плей/play` commands with no arguments will return help message;
* Fixed `очистить/clear` didn't cleared system messages;
* Fixed `юзер/user` didn't worked for bots;
* **\[Moderation\]** Moderation system improvements:
  * Warning duration support for command `пред/warn`;
  * Units support for warn/mute durations \(year, months, weeks, days, hours, minutes, seconds\);
  * Temporal bans support;
* Some small fixes and improvements.

### Version 7.3

* **\[music\]**
  * SoundCloud fixes \(again...\);
  * Yandex.Music track, playlists and albums playback has been implemented;
  * Music search will now use Yandex.Music instead or YouTube;
* Command `юзер/user` now contains last online date;
* **\[web\]** Message templates in panel mode now supports message outside of panel;
* **\[web\]** Alias custom command now ignores the prefix in its content;
* **\[web\]** Added new message template variables:
  * `{server.owner}`
  * `{member.level}`
  * `{member.voiceTime}`
  * `{member.cookies}`
* **\[Ranking\]** Fixed "Ranking is not available for this member";
* Following commands are now supporting ID as well as mention:
  * `юзер/user`
  * `аватар/avatar`
  * `бан/ban`
  * `кик/kick`
  * `мьют/mute`
  * `пред/warn`
  * `преды/warns`
  * `снятьпред/remwarn`
  * `размьют/unmute`
  * `очистить/clear`
  * `цвет/color`
* **\[audit\]** New audit action type "Messages has been cleared" which logs usage of command `очистить/clear` as well as keeps deleted content in audit channel;
* Command `бонус/bonus` now supports its disabling using minus sign: `!bonus -`;
* Updated status icons for `юзер/user` and platform icons for `steam` commands;
* Duration texts for mute commands has been fixed;
* Fixed `повтор/repeat` command;
* Some small fixes and improvements.

### Version 7.2

* Fix broken SoundCloud playback;
* Some small fixes and improvements.

### Version 7.1

* **\[web\]** Welcome option "Restore member's roles on re-join" was splited into two independent options for roles and nicknames;
* **\[ranking\]** New moderator command `уровень/level`can be used to change member's ranking level;
* **\[custom commands/bonus\]** Reaction roles using message custom command;

