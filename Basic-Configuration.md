# Basic Configuration

Here you will find basic configuration instructions and guidelines for the Carbon config. If there is a setting or option you are looking for here that you cannot find, please go to [Advanced Configuration](Advanced-Configuration). 
- The default config itself can be found at [`src/main/resources/config.yml`](https://github.com/Draycia/Carbon/blob/master/CarbonChat/src/main/resources/config.yml)

## Getting Started

Before you can begin to effectively configure Carbon, it is necessary to understand the basis of the plugin, and a little bit about how it works. Carbon is built on **channels**, or, different chats which people can see and send messages in, based on a variety of different factors. 

Some of these factors include [permissions](Permissions), especially the ability to send messages, and the ability to receive messages, in a particular channel, each of which is controlled by a separate permission. Another system of factors are [contexts](Contexts), which allow a person to interact with channels based off of factors like distance, mcMMO party, worldguard region, and towny town. 

Just about every single setting and format in Carbon is configurable, which allows for massive potential! Want a broadcast channel with a special format? Simply create it in the config, and only give your players permission to see the channel, not send messages. Make the channel unignorable, and \*bam*! a broadcast channel, exactly how you wanted.

With that covered, we will go over in a bit more detail the channel system, the basic options which most people will need to use, and the placeholders which Carbon supports in its formatting.

## Channels System

The channels system, as described above, is a powerful method of customizing chat exactly how you want it. Even if you want just one channel, it's a simple matter to configure it function exactly how you want it to! Here's an overview:

## Overview

___
### default
The `default:` section in the configuration is the first one, and it defines the standard attributes of every new channel, unless those attributes are specifically changed in that new channel. In other words, this section holds what the (customizable) formats are for every other channel unless you define different settings in them.

[**Click here for specifics of each option**](#default-specifics)
- [`switch-message`](#switch-message)
- [`switch-other-message`](#switch-other-message)
- [`switch-failure-message`](#switch-failure-message)
- [`toggle-on-message`](#toggle-on-message)
- [`toggle-off-message`](#toggle-off-message)
- [`toggle-other-on`](#toggle-other-on)
- [`toggle-other-off`](#toggle-other-off)
- [`cannot-use-channel`](#cannot-use-channel)
- [`formats`](#formats)
- [`contexts`](#contexts)
- [`color`](#color)
- [`ignorable`](#ignorable)
- [`should-bungee`](#should-bungee)
- [`primary-group-only`](#primary-group-only)
- [`default-group`](#default-group)
- [`cancel-message-event`](#cancel-message-event)
- [`honors-recipient-list`](#honors-recipient-list)
- [`custom-order`](#custom-order)

### channels

This section of the config is where you define channels and their attributes. Simply setting a channel up with a name will cause the channel to take on all the attributes that are set as [default](#default). To define things per-channel, that override default settings, simply set them as options with the same format as the examples already present in the config or in this wiki.

- `global` - the name of the channel that Carbon uses internally
- `name` - the name of the channel when used
- `aliases` - other names/letters by which a channel can be used
- `default` - whether the channel is the default channel which players send messages to (main chat)
- `message-prefix` - which symbol or character a message can begin with in order for it to be sent to that channel
###### Example
```yaml
staff:
  name: Staff
  formats:
    moderator: '<red>[Mod]<white><message>'
    developer: '<green>[Dev]<white><message>'
    admin: '<gold>[Admin]<red><message>'
  ignorable: false
  should-bungee: true
  message-prefix: '$'
  switch-message: '<color:#55FF55>Staff chat toggled. Time to whine to the developer? Click <green><click:run_command:"/fly">here<reset><color:#55FF55> to fly.'
  cannot-use-channel: '<red><bold><italic>You are not permitted to use staff channel!'
```

### formatting
 - `type` - This option allows you to choose what you would like to use for formatting - `Minimessage`, `MiniMessage-Markdown`, or `MineDown`. Note that all formatting in the default config is set up for `MiniMessage`, which is the default. If you change this, you will have to change the formatting style of the config.
###### Example
```yaml
type: MiniMessage
```

 ### language

 This section of the config is where non-channel related formats are set.
 
###### The following messages are compatible with MiniMessage/MineDown only
[**Click here for specifics of each option**](#language-specifics-no-papi-support) 
- [`reloaded`](#reloaded)
- [`message-to-other`](#message-to-other)
- [`message-from-other`](#message-from-other)
- [`spy-whispers`](#spy-whispers)
- [`no-reply-target`](#no-reply-target)
- [`empty-channel`](#empty-channel)
- [`channel-switch-failure`](#channel-switch-failure)
- [`other-nickname-set`](#other-nickname-set)

###### The following messages are compatible with PlaceholderAPI and MiniMessage/Minedown 
[**Click here for specifics of each option**](#language-specifics-papi-support) 
- [`me`](#me)
- [`ignoring-user`](#ignoring-user)
- [`not-ignoring-user`](#not-ignoring-user)
- [`ignore-exempt`](#ignore-exempt)
- [`channel-color-set`](#channel-color-set)
- [`spy-toggled-on`](#spy-toggled-on)
- [`spy-toggled-off`](#spy-toggled-off)
- [`spy-whispers-on`](#spy-whispers-on)
- [`spy-whispers-off`](#spy-whispers-off)
- [`nickname-set`](#nickname-set)

### server-name
This setting allows you to define what this server will appear as when you use the `<server>` placeholder in channel formats.
###### Example
```yaml
server-name: 'Hub'
```

### item-link-placeholders
This setting allows you to define what placeholders can be used in messages in order to link to the item a person is holding in their hand.
###### Example
```yaml
item-link-placeholders:
  - '[item]'
  - '%item%'
  - 'handitem'
  - '~inhand~'
```

### spy-prefix
This allows you to define what the prefix for the spy messages will be.

### pings
This section allows you to set up pings, a Carbon feature which will play a sound when a user is 'mentioned' in chat, kind of like a discord ping. 

- `enabled`
- `source`
- `sound`
- `volume`
- `pitch`
- `highlight`
- `on-whisper`

### storage
This section allows you to set your storage method. Currently JSON and MySQL are supported

###### Example
```yaml
type: MySQL # JSON, MySQL
  username: 'carbonuser'
  password: 'fjopeq1514375_nfo3416asndfo'
  database: 'mcserver'
  hostname: '45.74.856.14'
  port: 3306
```

### redis
This section allows you to configure redis.

###### Example
```yaml
enabled: false
  host: 'localhost'
  port: 6379
  database: 0
```


## Specifics
___

### Default Specifics

#### switch-message
- Defines the format of the message players receive when they enter the channel.
###### Example
```yaml
switch-message: '<green>You are now in <color><channel> <green>channel! Click <click:run_command:"/toggle <channel>">here<reset><green> to toggle it off.'
```

#### switch-other-message
- Defines the format others receive when you enter that channel.
###### Example
```yaml
switch-other-message: '<gray><player> </rainbow><gray>is now in <color><channel> <gray>chat!'
```

#### switch-failure-message
- Defines the format and message received by default when you cannot switch to a channel using `/channelname`
###### Example
```yaml
switch-failure-message: '<red>You cannot use channel <channel>!'
```

#### toggle-on-message
- Defines the format of the message you see when you toggle visibility of the channel on.
###### Example
```yaml
toggle-on-message: '<gray>You can now see <color><channel> <gray>chat!'
```

#### toggle-off-message
- Defines the format of the message you see when you toggle visibility of the channel off.
###### Example
```yaml
toggle-off-message: '<gray>You can no longer see <color><channel> <gray>chat!'
```

#### toggle-other-on
- Defines the format of the message that other players see when you toggle visibility of the channel on.
###### Example
```yaml
toggle-other-on: '<gray><player> </rainbow><gray>can now see <color><channel> <gray>chat!'
```

#### toggle-other-off
- Defines the format of the message that other players see when you toggle visibility of the channel off.
###### Example
```yaml
toggle-other-off: '<gray><player> </rainbow><gray>can no longer see <color><channel> <gray>chat!'
```

#### cannot-use-channel
- Defines the format of the message received when trying to use a channel one is not permitted to use. This includes `/<channelname>`, which is used to set one's active channel (so their messages go there) and `/<channelname> <message>`, which is used to send a message to that channel but notswitch their primary one to it.
###### Example
```yaml
cannot-use-channel: '<red>You cannot use that channel!'
```

#### formats
- This section of the config defines per-group formats, which is the user's primary group retrieved from [Vault](Installation#Requirements). The default configuration includes a format, which is by default the one that appears in all channels unless specified otherwise in that channel's settings.
###### Example
```yaml
staff: '<gray>{[%vault_prefix%<gray>]} %player_displayname% </rainbow><gray>» <color><message>'
default: '<gray>[%vault_prefix%<gray>] %player_displayname%</rainbow><gray>: <color><message>'
```

#### contexts
- This portion of the default channel config deals with chat contexts, which are systems by which channels apply to users by default. These are all set to `false` in this section. For more information on contexts and what they do, please see [this page on contexts](Contexts)
###### Example
```yaml
contexts:
  distance: -1
  mcmmo-party: false
  worldguard-region: false
  towny-town: false
  filter: true
  vault-balance: 0
  vault-cost: 0
```

#### color
- This setting defines the colour all channels are by default, unless overridden in a specific channel. When used it is the color that that `<color>` placeholder is replaced with. 
- It also supports PAPI, however the placeholder must result in a valid colour.
###### Example
```yaml
color: '#FFFF00'
```

#### ignorable
- This setting detemines if users can, by default, use the `/toggle` command for the channel it's set in, and stop seeing messages from it.   
###### Example
```yaml
ignorable: false
```

#### should-bungee
- This setting enables or disables cross server chat for channels by default, unless overridden in a specific channel.
###### Example
```yaml

```

#### primary-group-only
- This setting determines if Carbon will only set a non-default format for a user's primary group, or if it will set the format based on a search of all the user's groups, going with the first one it finds that the channel also has a specific format set for. ***It is highly recommended you leave this `true` because the order of groups which Vault sends is unreliable and should only be used if you know what you're doing!***
###### Example
```yaml
primary-group-only: true
```

#### default-group
- This setting determines which [Vault](Installation#Requirements) group is taken to be the `default` group for formatting purposes In other words, the group whose format the user will get if they do not have another group with a specified format for that channel.
###### Examle
```yaml
default-group: 'default'
```

#### cancel-message-event
- Will prevent other plugins from seeing messages that they should not do things with. This should be set to `false` for *public* channels, and to `true` for *private* channels. 
- This will ***not*** break compatibility with plugins like DiscordSRV which can still be used with private channels, even when set to `true`.
###### Example
```yaml
cancel-message-event: true
```

#### honors-recipient-list
- Used to allow other plugins to see who would recieve messages in a specific channel and is used for compatiblity. If you have another plugin which specifies what players receive certain messages, set this to true in the channel that plugin interacts in. Otherwise, leave it false.
###### Example
```yaml
honors-recipient-list: false
```

#### custom order
- This setting allows you to define an order of groups through which Carbon will check for the first match that the user has. It uses standard yaml array format.
###### Example
```yaml
custom-order: 
  - 'owner'
  - 'admin'
  - 'helper'
  - 'builder'
  - 'default'
```

### Language Specifics (No PAPI Support)

#### reloaded
- The message sent when Carbon successfully reloads
###### Example
```yaml
reloaded: '<Red>Chat config has been reloaded!'
```

#### message-to-other
- Format of private messages as seen when sent. `<target>` refers to the recipient of the private message.
###### Example
```yaml
message-to-other: '<green>[<gray>Me <gold>-> <gray><target></rainbow><green>] <message>'
```

#### message-from-other
- Format of private messages as seen when received. `<sender>` refers to the person sending the private message as seen when received.
###### Example
```yaml
 message-from-other: '<green>[<gray><sender></rainbow> <gold>-> <gray>Me<green>] <message>'
```

#### spy-whispers
- Format of spy-detected whispers between other players. `<sender>` refers to the person sending the message, and `<target>` refers to the person receiving it.
###### Example
```yaml
spy-whispers: '<yellow>Spy [<gray><sender></rainbow> <gold>-> <gray><target></rainbow><yellow>] <message>'
```

#### no-reply-target
- Message seen when a player tries to reply to private message when there are no private messages to reply to.
###### Example
```yaml
no-reply-target: '<red>You have no one to reply to!'
```

#### empty-channel
- Empty channel message, received when sending a message to a channel with nobody else in it.
###### Example
```yaml
empty-channel: '<blue>You're <italic>all alone</italic> in this channel, <bold>nobody</bold> to hear you, <bold>nobody</bold> to answer. No matter how long, how often, how <italic>desperately</italic> you communicate, the vast distance of infinity is too great here, insurmountable, rendering you totally and completely unable to reach another living soul.'
```

#### other-nickname-set
- Format of system message received when a player changes their nickname.
###### Example
```yaml
other-nickname-set: '<green><user></rainbow>''s nickname was set to <nickname><green>!'
```

#### other-nickname-reset
- Format of system message received when a player resets their nickname.
###### Example
```yaml
other-nickname-reset: '<green><user></rainbow>''s nickname was reset!'
```

### Language Specifics (PAPI Support)

#### me
- Defines the format of the message sent to the channel the user is in when they run the `/me <message>` command.
###### Example
```yaml
 me: '<italic><dark_purple>*%player_displayname% </rainbow><message>*</dark_purple></italic>'
```
#### ignoring-user
- Message received when a user is ignored. `<player>` refers to the ignored user. 
###### Example
```yaml
 ignoring-user: '<red>You have silenced <gold><player></rainbow><red> and will never hear from them again!'
```

#### not-ignoring-user
- Message received when a user is un-ignored. `<player>` refers to the un-ignored user.
###### Example
```yaml
not-ignoring-user: '<green>You have chosen to make audible the cries of <gold><player></rainbow> once more!'
```

#### ignore-exempt
- Message received when a player attempts to ignore someone that cannot be ignored. `<player>` refers to the unignorable user.
###### Example
```yaml
ignore-exempt: '<red>You may not silence <gold><player></rainbow>! <red>They are exempt from being ignored!'
```

#### channel-color-set
- Message received when setting a channel colour. `<color>` refers to the colour the channel is set to, `<channel>` to the name of the channel, and `<hex>` to the hex value of the `<color>`.
###### Example
```yaml
 channel-color-set: '<green>You have set <color><channel> <green>color to <hex>!'
```

#### spy-toggled-on
- Message received when toggling on spy for a channel. `<color>` refers to the color of the channel you toggled spy on for, and `<channel>` to its name.
###### Example
```yaml
spy-toggled-on: '<gray>You are now spying on <color><channel> <gray>chat!'
```

#### spy-toggled-off
- Message received when toggling off spy for a channel. `<color>` refers to the color of the channel you toggled spy off for, and `<channel>` to its name.
###### Example
```yaml
spy-toggled-off: '<gray>You are no longer spying on <color><channel> <gray>chat!'
```

#### spy-whispers-on
- Message received when toggling on spy for whispers, or private messages.
###### Example
```yaml
spy-whispers-on: '<gray>You are now spying on private messages!'
```

#### spy-whispers-off
- Message received when toggling off spy for whispers, or private messages.
###### Example
```yaml
spy-whispers-off: '<gray>You are no longer spying on private messages!'
```

#### nickname-set
- Message a player receives when they set their nickname.
###### Example
```yaml
nickname-set: '<green>Your nickname was set to <nickname></rainbow><green>!'
```

#### nickname-reset
- Message a player receives when they reset their nickname.
###### Example
```yaml
<purple>Your nickname was reset!
```


## Placeholders