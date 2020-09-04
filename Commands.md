# Commands

The following is a list of commands offered by the plugin, and their function. **All commands can be modified & disabled in [`commands.yml`](https://github.com/Hexaoxide/Carbon/blob/master/src/main/resources/commands.yml).**

Command | Aliases | Permission | Description
--- | --- | --- | ---
`/channellist` | `/chlist` | `carbonchat.channellist` | View all channels.
`/channel <name> [message]` | `/ch, /switch, /join` | `carbonchat.channel, carbonchat.channel.message` | Join specified chat channel, or send a message in a specific channel.
`/sudochannel <player> <channel> [message]` | `/sch, /sudochannel, /schannel, /chsudo, /channelsudo` | `carbonchat.channel.others` | Run /channel as another player.
`/toggle [player] <channel>` | `/togglechannel, /tch, /togglech, /tchannel, /togglec` | `carbonchat.toggle` | Toggle seeing a channel's messages for yourself or another player.
`/nickname [player] <name\|off>` | `/nick` | `carbonchat.nickname, carbonchat.nickname.others` | Set your nickname or another player's.
`/message <player> <message>` | `/msg, /whisper, /w` | `carbonchat.message` | Message another player privately.
`/reply <message>` | `/r` | `carbonchat.reply` | Reply to the last player who messaged you.
`/me <message>` | `/rp` | `carbonchat.me` | Show a message about yourself.
`/ignore <player>` | `/block` | `carbonchat.ignore` | Ignore another player.
`/mute <player>` | `/m` | `carbonchat.mute` | Server-mute a player.
`/shadowmute <player>` | `/sm, /smute` | `carbonchat.shadowmute` | Shadow mute a player.
`/spy <channel\|whispers>` | `/spych, /spychannel` | `carbonchat.spy, carbonchat.spy.channel` | Spy on a specific channel or player messages.
`/setcolor <channel> <color>` | `/setcolor` | `carbonchat.setcolor` | Set the specified channel's chat color.
`/clearchat` | `/clear, /cc` | `carbonchat.clearchat` | Clear chat.
`/chatreload` | `/creload, /cr` | `carbonchat.reload` | Reload CarbonChat configuration.
