# Commands

**All commands can be modified & disabled in <a href="https://github.com/Hexaoxide/Carbon/blob/master/src/main/resources/commands.yml"><code>commands.yml</code></a>.**

<table>
    <thead>
        <tr>
            <th>Command</th>
            <th>Aliases</th>
            <th>Permission</th>
            <th>Description</th>
        </tr>
    </thead>
    <tr>
        <td>
            <div><code>/channellist</code></div>
        </td>
        <td>
            <div><code>/chlist</code></div>
        </td>
        <td>
            <code>carbonchat.channellist</code>
        </td>
        <td>
            View all channels.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/channel &lt;name> [message]</code></div>
        </td>
        <td>
            <div><code>/ch, /switch, /join</code></div>
        </td>
        <td>
            <code>carbonchat.channel</code>
        </td>
        <td>
            Join specified chat channel, or send a message in a specific channel.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/sudochannel &lt;player> &lt;channel> [message]</code></div>
        </td>
        <td>
            <div><code>/sch, /sudochannel, /schannel, /chsudo, /channelsudo</code></div>
        </td>
        <td>
            <code>carbonchat.channel.others</code>
        </td>
        <td>
            Run /channel as another player.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/toggle [player] &lt;channel></code></div>
        </td>
        <td>
            <div><code>/togglechannel, /tch, /togglech, /tchannel, /togglec</code></div>
        </td>
        <td>
            <code>carbonchat.toggle</code>
        </td>
        <td>
            Toggle seeing a channel's messages for yourself or another player.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/nickname [player] &lt;name|off></code></div>
        </td>
        <td>
            <div><code>/nick</code></div>
        </td>
        <td>
            <code>carbonchat.nickname, carbonchat.nickname.others</code>
        </td>
        <td>
            Set your nickname or another player's.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/message &lt;player> &lt;message></code></div>
        </td>
        <td>
            <div><code>/msg, /whisper, /w</code></div>
        </td>
        <td>
            <code>carbonchat.message</code>
        </td>
        <td>
            Message another player privately.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/reply &lt;message></code></div>
        </td>
        <td>
            <div><code>/r</code></div>
        </td>
        <td>
            <code>carbonchat.reply</code>
        </td>
        <td>
            Reply to the last player who messaged you.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/me &lt;message></code></div>
        </td>
        <td>
            <div><code>/rp</code></div>
        </td>
        <td>
            <code>carbonchat.me</code>
        </td>
        <td>
            Show a message about yourself.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/ignore &lt;player></code></div>
        </td>
        <td>
            <div><code>/block</code></div>
        </td>
        <td>
            <code>carbonchat.ignore</code>
        </td>
        <td>
            Ignore another player.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/mute &lt;player></code></div>
        </td>
        <td>
            <div><code>/m</code></div>
        </td>
        <td>
            <code>carbonchat.mute</code>
        </td>
        <td>
            Server-mute a player.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/shadowmute &lt;player></code></div>
        </td>
        <td>
            <div><code>/sm, /smute</code></div>
        </td>
        <td>
            <code>carbonchat.shadowmute</code>
        </td>
        <td>
            Shadow mute a player.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/spy &lt;channel|whispers></code></div>
        </td>
        <td>
            <div><code>/spych, /spychannel</code></div>
        </td>
        <td>
            <code>carbonchat.spy, carbonchat.spy.channel</code>
        </td>
        <td>
            Spy on a specific channel or player messages.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/clearchat</code></div>
        </td>
        <td>
            <div><code>/clear, /cc</code></div>
        </td>
        <td>
            <code>carbonchat.clearchat</code>
        </td>
        <td>
            Clear chat.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/setcolor &lt;channel> &lt;color></code></div>
        </td>
        <td>
            <div><code>/setcolor</code></div>
        </td>
        <td>
            <code>carbonchat.setcolor</code>
        </td>
        <td>
            Set the specified channel's chat color.
        </td>
    </tr>
    <tr>
        <td>
            <div><code>/chatreload</code></div>
        </td>
        <td>
            <div><code>/creload, /cr</code></div>
        </td>
        <td>
            <code>carbonchat.reload</code>
        </td>
        <td>
            Reload CarbonChat configuration.
        </td>
    </tr>
</table>
