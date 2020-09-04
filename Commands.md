# Commands

All commands can be modified & disabled in <a href="https://github.com/Hexaoxide/Carbon/blob/master/src/main/resources/commands.yml"><code>commands.yml</code></a>.**

Command | Aliases | Permission | Description
| --- | --- | --- | --- |
 /channellist | /chlist | carbonchat.channellist | View all channels.
/channel &lt;name> [message] | /ch, /switch, /join | carbonchat.channel | Join specified chat channel, or send a message in a specific channel.
/sudochannel &lt;player> &lt;channel> [message]| /sch, /sudochannel, /schannel, /chsudo, /channelsudo | carbonchat.channel.others | Run /channel as another player.
/toggle [player] &lt;channel> | /togglechannel, /tch, /togglech, /tchannel, /togglec | carbonchat.toggle | Toggle seeing a channel's messages for yourself or another player.
/nickname [player] &lt;name|off> | /nick | carbonchat.nickname, carbonchat.nickname.others | Set your nickname or another player's.
/message &lt;player> &lt;message> | /msg, /whisper, /w | carbonchat.message | Message another player privately.
/reply &lt;message> | /r | carbonchat.reply | Reply to the last player who messaged you.
/me &lt;message> | /rp | carbonchat.me| Show a message about yourself.
/ignore &lt;player> | /block | carbonchat.ignore | Ignore another player.
/mute &lt;player> | /m | carbonchat.mute | Server-mute a player.
/shadowmute &lt;player> | /sm, /smute | carbonchat.shadowmute | Shadow mute a player.
/spy &lt;channel|whispers> | /spych, /spychannel | carbonchat.spy, carbonchat.spy.channel | Spy on a specific channel or player messages.
/clearchat | /clear, /cc | carbonchat.clearchat | Clear chat.
/setcolor &lt;channel> &lt;color> | /setcolor | carbonchat.setcolor | Set the specified channel's chat color.
/chatreload | /creload, /cr | carbonchat.reload | Reload CarbonChat configuration.
