# Commands

The following is a list of commands offered by the plugin, and their function. **All commands can be modified & disabled in [`commands.yml`](../blob/master/src/main/resources/commands.yml).**

Command | Aliases | Permission | Description
--- | --- | --- | ---
`/channellist` | `/chlist` | [`carbonchat.channellist`](../wiki/Permissions#channellist) | View all channels.
`/channel <name> [message]` | `/ch, /switch, /join` | [`carbonchat.channel`](../wiki/Permissions#channel), [`carbonchat.channel.message`](../wiki/Permissions#channelmessage) | Join specified chat channel, or send a message in a specific channel.
`/sudochannel <player> <channel> [message]` | `/sch, /sudochannel, /schannel, /chsudo, /channelsudo` | [`carbonchat.channel.others`](../wiki/Permissions#channelothers) | Run /channel as another player.
`/toggle [player] <channel>` | `/togglechannel, /tch, /togglech, /tchannel, /togglec` | [`carbonchat.toggle`](../wiki/Permissions#toggle) | Toggle seeing a channel's messages for yourself or another player.
`/nickname [player] <name\|off>` | `/nick` | [`carbonchat.nickname`](../wiki/Permissions#nickname), [`carbonchat.nickname.others`](../wiki/Permissions#nicknameothers) | Set your nickname or another player's.
`/message <player> <message>` | `/msg, /whisper, /w` | [`carbonchat.message`](../wiki/Permissions#message) | Message another player privately.
`/reply <message>` | `/r` | [`carbonchat.reply`](../wiki/Permissions#reply) | Reply to the last player who messaged you.
`/me <message>` | `/rp` | [`carbonchat.me`](../wiki/Permissions#me) | Show a message about yourself.
`/ignore <player>` | `/block` | [`carbonchat.ignore`](../wiki/Permissions#ignore) | Ignore another player.
`/mute <player>` | `/m` | [`carbonchat.mute`](../wiki/Permissions#mute) | Server-mute a player.
`/shadowmute <player>` | `/sm, /smute` | [`carbonchat.shadowmute`](../wiki/Permissions#shadowmute) | Shadow mute a player.
`/spy <channel\|whispers>` | `/spych, /spychannel` | [`carbonchat.spy`](../wiki/Permissions#spy), [`carbonchat.spy.channel`](../wiki/Permissions#spychannel) | Spy on a specific channel or player messages.
`/setcolor <channel> <color>` | `/setcolor` | [`carbonchat.setcolor`](../wiki/Permissions#setcolor) | Set the specified channel's chat color.
`/clearchat` | `/clear, /cc` | [`carbonchat.clearchat`](../wiki/Permissions#clearchat) | Clear chat.
`/chatreload` | `/creload, /cr` | [`carbonchat.reload`](../wiki/Permissions#reload) | Reload CarbonChat configuration.
