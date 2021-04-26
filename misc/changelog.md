---
description: The latest JuniperBot changes are described here.
---

# Changelog

### Version 9.23

#### Web

* Website interface was slightly updated to match actual Material Design guidelines;
* New "Notifications" dashboard section as replacement for welcoming section:
  * Welcome/leave notifications settings was moved here;
  * Added a new notification for Nitro Boost servers \(it has few limitations, check explanation message in dashboard\);
  * Added an options to disable ban/kick/warn DM notifications;
* Starting roles and roles restore settings were moved to Common settings;
* Allowed/ignored channel settings now contains a channel categories available for selection;
* Added an options to specify Minimal time duration between notifications for Twitch subscriptions;

#### Template engine

* Added an option to add a message reactions to the template message itself and to `createEmbed` builder;
  * **Note:** It is limited to 1 reaction per message for servers without bonus and to 5 reactions per messages for servers with bonuses;
* Added a new variable with server boost count: `{{ guild.boostCount }}`;

#### Other

* Added a "Member screening" support. Now bot will not any starting roles until member successfully pass the member screening and agree with server rules;
* `reminder/напоминание` command now supports "today" syntax, just specify time without date;
* Fixed an issue with unmute in private channels in case if muted member was granted an access to this channel using direct permission overrides;
* Fixed an issue with mute caused by managed role access rights update mechanism:
  * **Note:** You can enable managed role back again if you disabled it because this issue;
* Fixed an issue with the audit unwarn messages were sent even if those warns were removed earlier;
* Fixed an issue with forest fuss when single person could get a few player positions in lobby;
* Some internal fixes and improvements.

### Version 9.22

#### Music

* Update Lavaplayer library base to the latest at the moment \(1.3.67\);
* Fixed an issues with SoundCloud playback.

#### Dashboard

* Audit settings now has a hint with useful information about webhooks management;
* Content length of alias custom command now accepts up to 20000 characters reserved for template engine code;
* Added an option to disable reposts publishing in Vk.com subscriptions;
* Added an option to disable public ranking Web page.

#### Moderation

* Added a success/error emoji icons to corresponding command messages;
* Added a success messages for `бан/ban` and `кик/kick` commands with detailed information;
* Reasons of `бан/ban` now contains a duration if specified;
* Improved information content of `очистить/clear` command;
* Added an option to words filter allowing matching only whole words whitespace separated or partial matches;
* Auto-moderation filter notifications can't be sent to direct messages anymore \(I'm sorry\);
* Owner's messages will not be deleted anymore in case owner has muted role assigned.

#### Other

* Fixed an issue with `ранг/rank` command when it always mentioned members if replies system were enabled;
* Some internal fixes and improvements.

### Version 9.21

* Fixed an issue with voice role removed if user switched between voice channels with the same role assigned;
* Fixed an issue with messages weren't deleted for mutes members if their messages are replies;
* Fixed an issue with mute role restoring for rejoined members;
* Some small fixes and improvements.

### Version 9.20

* Discord Reply feature integration:
  * Bot now replies to commands \(both internal and custom\);
  * Auto-Moderation now replies to infractions;
  * Reminders now replies to commands created them \(works only with newly created reminders\);
  * It is possible to turn it on and off in common settings of dashboard \(disabled by default\);
* Fixed an issue with mute role restored on re-join even if mute is not valid anymore;
* Some small fixes and improvements.

### Version 9.19

* **\[audit\]** Audit system now works over webhooks instead of sending messages directly;
* Implemented a lot of internal optimizations and stability improvements;
* Some small fixes and improvements.

### Version 9.18

* Fixed an issue with existing permission overrides in text channels getting granted send message permission for unmuted members \(now it clears into "/"\);
* Fixed an issue with member names broken in titles of some commands if they contained Markdown sequences \(moderation, music\);
* Fixed an issue with YouTube music searching;
* Some small fixes and improvements.

### Version 9.17

* **\[web\]** Added a moderation option allowing moderators with higher role to punish other moderators with lower role;
* **\[web\]** Message templates improvements:
  * Added a new global variable `bot` as Member instance of bot;
  * Attributes references improvements;
* `лидеры/leaders` command now accepts emojis as sort options \(🏆 \| 🎤 \| 🍪\);
* Fixed an issue with YouTube channel search at subscriptions;
* Fixed an issue with clear command cleared webhooks messages with specified member;
* Fixed an issue with member names broken in titles of `лидеры/leaders` commands if they contained Markdown sequences;
* Some small fixes and improvements.

### Version 9.16

* Some `осебе/bio` command improvements;
* **\[web\]** Message templates improvements:
  * Toolbar improvements \(link, roles, channels insertion\);
  * Template engine now supports Elvis operator \(`<expression> ?: <default_value>`\);
* Fixed an issue with member names broken in titles of `юзер/user`, `аватар/avatar` commands if they contained Markdown sequences;
* Fixed an issue with auto-moderation links trigger not worked correctly with empty whitelist;
* Some small fixes and improvements.

### Version 9.15

* vk.com integration improvements:
  * Added an option to hide community URL in post footers;
  * Fixed an issue when URLs containing markdown characters were broken;
* Moderation audit logs like ban/kick/mute/warn now contains the link to command or infraction message;
* Added an option to restore all starting roles on member's rejoin;
* Fixed an issue with embed color of `лис/fox` command;
* Fixed an issue with hidden owner of `сервер/serverinfo` command;
* **\[web\]** Fixed an issue when shard searching by server id worked incorrectly;
* Some small fixes and improvements.

### Version 9.14

* vk.com integration improvements:
  * Updated API version to 5.101;
  * Added a reposts support;
  * Added an ability to filter posts using keywords;
  * Added an ability to specify custom message \(useful for roles mentions\);
* Fixed an issue when flood auto-moderation filter triggered for message updates;
* Some small fixes and improvements.

### Version 9.13

* Command `сервер/serverinfo` improvements:
  * Removed "Cached" entry;
  * Displays server's banner if exists;
* **\[Music\]** Added a `продвинуть/promote` command allowing to promote specified song as next in playback queue;
* Command `бонус/bonus` now has an option to show payment list;
* Some small fixes and improvements.

### Version 9.12

* Fixed an issue with Forest Fuss DM actions not worked correctly;
* Command help message accessed by `?` sign will not be deleted anymore;
* Command `юзер/user` now shows Spotify playback information;
* Some small fixes and improvements.

### Version 9.11

* Message templates improvements:
  * Now you can activate strict mode manually, check `use` tag in a documentation;
  * Dates are now display in correct language by default without using `date` function;
* Fixed a message about unknown user in ban command;
* Added a `разбан/unban` command allowing to unban member by his ID, name or tag;
* Command `сервер/serverinfo` updated;
* Command `очистить/clear` updated;
* Some small fixes and improvements.

### Version 9.10

* Message templates improvements:
  * A strict mode has been implemented which means that attempt to access undefined variable or non-existent property/function will lead to template compilation error;
  * **Embed** now supports update existent message by its id \(`update` function instead of `send`\);
  * New `everyone/here` mention control. In case if they are forbidden, they will not be masked by invisible character but disabled;
* Auto-moderation links filter now will not trigger on the invites created for your own server \(requires **Manage Server** permission\);
* Fixed an issue with duplicated command executions;
* Some small fixes and improvements.

### Version 9.9

* Fixed broken `викифур/wikifur` command;
* Fixed public mentions `@everyone/@here` not worked correctly in reminders created at the dashboard;
* **\[web\]** Fixed issues with dashboard settings messed after switching between tabs few times;
* Added an option to let repeatable reminders work continuously even if there is no activity on the channel;
* Some small fixes and improvements.

### Version 9.8

* Zalgo filter now ignores mentions;
* Ranking top by voice activity and cookies:
  * Using command `лидеры/leaders`;
  * Using ranking page on the website;
* **\[donate\]** Start date for repeatable reminders;
* **\[forest fuss\]** Now all players can skip current game step if they need to \(for example if someone went AFK\);
* **\[audit\]** Audit system improvements:
  * Bot add/leave actions now works correctly;
  * **\[web\]** Ignored text channels for message edit/delete/clear logs;
* Now you can configure the delay before system messages deletion for both success and error messages;
* Fixed some issues with emojis detection in message templates;
* Fixed an issue with permanent mute using auto-moderation filters;
* Some small fixes and improvements.

### Version 9.7

* Extended Reminder System:
  * Command `напомни/remind` has been renamed to `напоминание/reminder`;
  * Now you're able to check server's reminder list and remove reminders you don't need anymore;
  * Command syntax has been changed, check command help to see what changed;
  * Now you can control reminders using dashboard;
  * **\[donate\]** Repeatable reminders with intervals;
* Now bot will not delete user's messages if he has a mute role in case it is not managed. This giving administrator full control over mute role;
* Fixed some issues with mentions detection in message templates;
* Some small fixes and improvements.

### Version 9.6

* Message template improvements:
  * New property for **Member**: `tag` - returns user's tag in format `Name#1234`;
  * Fixed an issue with functions accepting `null` as parameters;
* **\[audit\]** Added a new action type logging for removed and reset warnings;
* Command `бонус/bonus` is not unavailable for configuring and enabled permanently for everyone;
* Prefix cannot contain "\`" character now;
* Fixed issues with text formatting of YouTube/Twitch notifications, and their preview images should display correctly now;
* Fixed an issue with cooldown was not available for longer than 17 days;
* Some small fixes and improvements.

### Version 9.5

* Message template improvements:
  * Fixed an confusion with the names of ranking variables:
    * Variable `member.rank.remainingExp` changed - now returns remaining EXP until the next level rather than the current EXP on the current level;
    * Variable`member.rank.levelCurrentExp` added - returns current EXP on the current level;
  * Fixed an issues with some function invocations;
* Auto-moderation improvements:
  * New filter has been added: Zalgo;
  * New restraints have been added: mute and change roles;
* Fixed an issue with infinite rounds of Forest Fuss caused by Fox and Beaver gameplay conflict;
* Some small fixes and improvements.

### Version 9.4

* Bonus system update:
  * Now there is no explicit binding of bonuses to the server owner and bonuses can be activated on absolutely any servers, you don't have to be an owner now;
  * Due to the lack of binding, the number of available servers with bonuses is now limited:
    * **Patreon**: number is equal of subscription amount \($2 - 2 servers, $5 - 5 servers\);
    * **Nitro-Booster**: any single server you want;
  * Command `бонус/bonus` has been updated, now it allows to manage bonuses on the servers:
    * Activate/deactivate bonuses on current on selected server by ID;
    * Show the list of active bonuses;
  * New subscription option through Boosty.to: [https://boosty.to/juniperbot](https://boosty.to/juniperbot)
* If member speaking in voice channel while global muting, he will be kicked from voice channel;
* Redesigned interface of embed fields editor in message templates and a list of reaction roles in custom commands;
* Some small fixes and improvements.

### Version 9.3

* Message template improvements:
  * Fixed an issue when Attribute's functions `increment`/`decrement` not worked correctly for some input;
* Fixed an issue when VK.com reposts caused an empty messages with only `@everyone` if it was enabled;
* `сервер/serverinfo` command improvements: reordered some fields, added a bonus status field with thanks message;
* Mutes improvements:
  * Added new mute mode `here` additionally to `everywhere`;
  * **\[web\]** Added an option to select default mute mode so you can mute members on the whole server by default without `everywhere` keyword;
  * **\[web\]** Added an option to select muted role and disable an automated management of its permissions in the channels;
* **\[audio\]** Fixed an issue with loading some user's Yandex.Music playlists;
* `слоумод/slowmode` commands now supports duration up to 21600 seconds;
* Some small fixes and improvements.

### Version 9.2

* Message template improvements:
  * Ability to store your own custom member's data \(attributes\)
  * New data types:
    * **Attribute** - member attribute;
  * New property for **Rank**: `voiceActivityMs` - voice activity of member in milliseconds; 
  * NEw functions for **Member**:
    * `modifyNickname('Name')` - change member's nickname;
    * `getAttribute('key')` - get member's attribute object with key `key`;
* Huge commands Help information update:
  * **\[web\]** New command dictionary https://juniper.bot/commands;
  * **\[web\]** It is integrated as dashboard's commands settings too;
  * Now you can get help information for every command using `?`sign, for example `!юзер ?`;
* Some small fixes and improvements.

### Version 9.1

* Message template improvements:
  * New global functions:
    * `startsWith` - checks if string starts with specified prefix string;
    * `endsWith` - checks if string ends with specified suffix string;
    * `contains` - check if string contains other substring;
    * `plural` - selects word plural for specified number;
  * New data types:
    * **Category** - channel category;
    * **Attachment** - message attachment;
    * **Embed** - message embed for sending;
  * New **TextChannel** functions: `createEmbed()` - create new message embed;
  * New property for **TextChannel** and **VoiceChannel**: `parent` - returns channel category if exists; 
  * New property for **Member**: `bot` - true if this member is bot; 
  * New property for **Message**: `attachments` - attachments list; 
  * Fixed an issue when ranking variables `rolesToAdd`, `rolesToRemove` not worked correctly;
  * Fixed an issue when variable `{{member.rank.rank}}` always returned 0;
  * Fixed an issue when message content was duplicated inside embed content in case it was empty;
  * Fixed an issue when backspace button not worked correctly inside message templates on mobile devices;
* **\[Web\]** Enable/disable switch state of auto-moderation filters will now be saved immediately;
* **\[Web\]** Fixed an issue when any subscription errors were not displayed correctly;
* Some small fixes and improvements.

### Version 9.0

* ~~JuniperScript~~ Template engine:
  * Extended template variables;
  * Expressions, algorithms, conditions;
  * Actions as part of template: role add/remove, send messages, check permissions;
  * Documentation: [https://docs.juniper.bot/features/template-engine](https://docs.juniper.bot/features/template-engine);
  * Examples: [https://docs.juniper.bot/features/template-engine/examples](https://docs.juniper.bot/features/template-engine/examples);
* **\[Аудио\]** Improved `очередь/queue` command;
* Command settings improvements:
  * Ability to hide the command;
  * Ability to limit the command to NSFW channels;
  * Separate save, save and close actions;
  * Ability to duplicate commands;
  * Now you can save using Ctrl+S hotkey;
* **\[web\]** Improved bad words insertion in automoderation filter \(split by spaces, commas\);
* Fixed an issue when actions per infractions with permanent duration not worked correctly, whoops;
* Fixed an issue when `ковид/covid` not worked at all;
* Some small fixes and improvements.

### Version 8.9

* Fixed an issue when non-default accent color of messages not worked at custom commands, they had default orange;
* **\[Audit\]** Improved audit forwarding settings, now you can specify individual channel per each action type;
* Fixed an issues with performance on some shards;
* Some small fixes and improvements.

### Version 8.8

* **\[donate\]** Reaction roles improvements:
  * Now you can add multiple roles per one reaction;
  * New you can enable singular mode allowing to select roles of only one last selected reaction removing all previous;
* Fixed an issue when JB-MUTED role has been force created by `unmute` command;
* Fixed an issue when bot deleted all user's messages who was unmuted manually by removing channel's permission override;
* Fixed an issue when Mole of forest fuss was able to check multiple players at once;
* Fixed an issues with music playback;
* Some small fixes and improvements.

### Version 8.7

* Custom commands improvements:
  * Reserved command names restriction has been removed;
  * Command names now can contain any characters except spaces;
  * Improved `{content}` variable, now it supports arguments range:
    * `{content:2..5}` - inserts arguments from second to fifth;
    * `{content:2..}` - inserts second and all following arguments;
    * `{content:..5}` - inserts arguments from first to fifth;
* Fixed an issue when key words of commands `color/цвет` and `remind/напомни` were localized by interface language;
* Fixed an issue when unused color roles didn't deleted;
* Fixed an issue when bot didn't stopped the playback if he was removed from channel manually;
* Any duration command now supports minutes as `m`/`м`;
* Success message of temporary role granting will not be removed now;
* New command `covid/ковид` with information about world COVID-19 situation;
* Some small fixes and improvements.

### Version 8.6

* **\[Moderation\]** Moderation system improvements:
  * Now you don't have to mention member to remove his warnings, just use case number instead;
  * Added a new command `temprole/времроль` can be used to give roles temporary;
  * Added a new command `resetwarns/сброспред`can be used to reset all warnings on server or just for @mentioned member;
* **\[Audit\]** Added a new action type for roles changing logging;
* **\[web\]** Dark Theme has been implemented \(you can turn it on/off using button at site footer\);
* **\[web\]** Commands search has been implemented;
* Added a new command `emote/эмоция` can be used to get detailed information about emote, emoji or characters;
* Remind message and result of `!t` command now implemented as embed messages;
* Fixed an issue when new members getting reward role for level 0;
* Fixed an issue when some youtube subscriptions weren't listed in search results ;
* Some small fixes and improvements.

### Version 8.5

* **\[web\]** Website improvements:
  * Colors reset button has been added to rank card;
  * Website navigation and footer has been updated \(language change and useful links\);
  * Added a "Terms of Service" section: [https://juniper.bot/terms](https://juniper.bot/terms);
  * Added a "Privacy Policy" section: [https://juniper.bot/privacy](https://juniper.bot/privacy);
  * Now all tabs of dashboard have their own links;
  * Delayed message removing option has been added to all message templates;
* Fixed an issue when capslock filter triggered on some mentions or emoji names;
* Fixed an issue when warning didn't flushed on reaching maximum level of warning infractions;
* Starting roles will not be assigned if roles restore on rejoin was enabled and there is any role to restore;
* Updated `warns/преды` to support pagination;
* Some small fixes and improvements.

### Version 8.4

* **\[Donate\]** Now you can customize default ranking card of your whole guild;
* Now you can view full list of custom commands with their descriptions using `help custom/хелп польз`;
* `leaders/лидеры` command now supports pagination;
* White list option of invite codes has been added to links filter;
* Now member will disappear from ranking list if his ranking got reset \(manually or if he left guild\);
* Some small fixes and improvements.

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

