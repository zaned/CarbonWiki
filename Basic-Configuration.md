# Basic Configuration

Here you will find basic configuration instructions and guidelines for the Carbon config. If there is a setting or option you are looking for here that you cannot find, please go to [Advanced Configuration](Advanced-Configuration). 

## Getting Started

Before you can begin to effectively configure Carbon, it is necessary to understand the basis of the plugin, and a little bit about how it works. Carbon is built on **channels**, or, different chats which people can see and send messages in, based on a variety of different factors. 

Some of these factors include [permissions](Permissions), especially the ability to send messages, and the ability to receive messages, in a particular channel, each of which is controlled by a separate permission. Another system of factors are [contexts](Contexts), which allow a person to interact with channels based off of factors like distance, mcMMO party, worldguard region, and towny town. 

Just about every single setting and format in Carbon is configurable, which allows for massive potential! Want a broadcast channel with a special format? Simply create it in the config, and only give your players permission to see the channel, not send messages. Make the channel unignorable, and \*bam*! a broadcast channel, exactly how you wanted.

With that covered, we will go over in a bit more detail the channel system, the basic options which most people will need to use, and the placeholders which Carbon supports in its formatting.

## Channels System

The channels system, as described above, is a powerful method of customizing chat exactly how you want it. Even if you want just one channel, it's a simple matter to configure it function exactly how you want it to! Here's an overview:

### default
- The `default:` section in the configuration is the first one, and it defines the standard attributes of every new channel, unless those attributes are specifically changed in that new channel. In other words, this section holds what the (customizable) formats are for every other channel unless you define different settings in them.
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

## Placeholders