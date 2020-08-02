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

- `switch-message`
- `switch-other-message`
- `toggle-on-message`
- `toggle-off-message`
- `toggle-other-on`
- `toggle-other-off`
- `cannot-use-channel`
- `me-format`
- `formats`
- `contexts`
- `color`
- `ignorable`
- `forward-format`
- `should-bungee`
- `format-group`

### channels

This section of the config is where you define channels and their attributes. Simply setting a channel up with a name, aliases, and [default toggle](), will cause the channel to take on all the attributes that are set in [default](Basic-Configuration#default). To define them per-channel, simply set them as options with the same format as the examples.

- `global` - the name of the channel that Carbon uses internally
- `name` - the name of the channel when used
- `aliases` - other names/letters by which a channel can be used
- `default` - whether the channel is the default channel which players send messages to (main chat)

### formatting
 - `type` - This option allows you to choose what you would like to use for formatting - `Minimessage`, `MiniMessage-Markdown`, or `MineDown`. Note that all formatting in the default config is set up for `MiniMessage`, which is the default. If you change this, you will have to change the formatting style of the config.

 ### language

 This section of the config is where non-channel related formats are set. 

###### The following message are compatible with MiniMessage/MineDown only
- `reloaded`
- `message-to-other`
- `message-from-other`
- `spy-whispers`
- `no-reply-target`
- `empty-channel`
- `channel-switch-failure`
- `other-nickname-set`

###### The following messages are compatible with PlaceholderAPI and MiniMessage/Minedown 
- `ignoring-user`
- `not-ignoring-user`
- `ignore-exempt`
- `channel-color-set`
- `spy-toggled-on`
- `spy-toggled-off`
- `spy-whispers-on`
- `spy-whispers-off`
- `nickname-set`

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
#### switch-message
- Defines the format of the message players receive when they enter the channel.

#### switch-other-message
- Defines the format others receive when you enter that channel.

#### toggle-on-message
- Defines the format of the message you see when you toggle visibility of the channel on.

#### toggle-off-message
- Defines the format of the message you see when you toggle visibility of the channel off.

#### toggle-other-on
- Defines the format of the message that other players see when you toggle visibility of the channel on.

#### toggle-other-off
- Defines the format of the message that other players see when you toggle visibility of the channel off.

#### cannot-use-channel
- Defines the format of the message received when trying to use a channel one is not permitted to use. This includes `/<channelname>`, which is used to set one's active channel (so their messages go there) and `/<channelname> <message>`, which is used to send a message to that channel but notswitch their primary one to it.

#### me-format
- Defines the format of the message sent to the channel the user is in when they run the `/me <message>` command.

#### formats
- This section of the config defines per-group formats, which is the group retrieved from vault that is a user's primary group. The default configuration includes a format, which is by default the one that appears in all channels unless specified otherwise in that channel's settings.

#### contexts
- This portion of the default channel config deals with chat contexts, which are systems by which channels apply to users by default. These are all set to `false` in this section. For more information on contexts and what they do, please see [this page on contexts](Contexts)

#### color
- This setting defines the colour all channels are by default, unless overridden in a specific channel.

#### ignorable
- This setting detemines if users can, by default, use the `/toggle` command for channels and stop seeing messages from them   

#### forward-format
- This setting determines whether channels by default will re-format the message if sent from another server. It is set to false by default as it is not recommended you do this unless you have a channel setup which absolutely requires it.

#### should-bungee
- This setting enables or disables cross server chat for channels by default, unless overridden in a specific channel.

#### format-group
- `primary only` - This setting will cause the chat format for the user need to match their primary group, else it will use the one for the default group. 
- `vault-sorting` - This setting will go through a list of their groups in an order ***that is not set in a reliable way in every situation*** and use the first it finds. As such it is not recommended unless you know what you're doing!
- `custom` - This setting allows you to define an order of groups through which Carbon will check for the first match that the user has. It uses standard yaml array format, and it is recommended you use this over `vault-sorting` in order to ensure consistency. 

## Placeholders