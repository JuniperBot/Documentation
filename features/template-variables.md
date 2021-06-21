# Template Variables \(Deprecated!\)

{% hint style="danger" %}
This section is **deprecated**. New template engine have been introduced in version 9.0. There is no English translation just yet but you can use Google Translate: [Click here](https://docs.juniper.bot/features/message-templates).

We do not recommend to use the old template variables as they aren't supported anymore and will be deleted eventually.

Shourtly, you should do the following:  
1. Make them use double brackets:  
`{member}` replaced by `{{member}}`   
2. Variable `server` is `guild`now:  
`{server}` replaced by`{{guild}}`  
`{server.name}` replaced by `{{guild.name}}`   
3. Dates are working differently:  
`{currentTime}` replaced by `{{date('now')}}`  
Old date variable with short formats will not work anymore, you should use date function with the format you need.  
4. In ranking variable `{level}` replaced by `{{member.rank.level}}`   
5. In custom commands:  
`{content}` replaced by `{{arguments}}`  
`{content:1}` replaced by `{{arguments.get(1)}}`  
`{content:1..}` replaced by `{{arguments.after(1)}}`  
`{content:..4}` replaced by `{{arguments.before(4)}}`  
`{content:2..4}` replaced by `{{arguments.range(2,4)}}`   
and so one, use your own ranges.  
6. Mentions are working differently now:  
`{message.mentions}` replaced by `{{join(message.mentionedMembers)}}`  
`{message.mentions.1}` replaced by `{{message.mentionedMembers[0]}}`  
`{message.mentions.2}` replaced by `{{message.mentionedMembers[1]}}`   
Note that count starts from 0 now.
{% endhint %}

