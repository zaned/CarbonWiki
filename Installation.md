# Installation

To install Carbon, all you need to do is drop the plugin into your server's `plugins` folder, and start the server. The rest of the file creation will be handled by the plugin the first time you start it. 

## Setup

Setting up Carbon is fairly simple. For the basics, you go into the [configuration folder](Basic-Configuration) and edit the default channel settings to have the attributes you desire it to have. This includes a set of system messages that appear when the default channel is interacted with, the formats for groups named `default` and `staff`, and several context options, all of which apply by default to any channel you create. To override these, simply **add the settings in another channel name below and within that channel, those added settings will apply.**

Most of the settings in the default configuration are intended as examples, and it is encouraged that you modify them in order to achieve your desired chat format. [Contexts](Contexts), which are options included in the config, are disabled by default, though they can be also easily be modified to match your desired specifications.

## Requirements

For Carbon to start up, no other plugins are required. However, in order to retrieve prefixes and other formatting from a permissions plugin ([See Luckperms](https://github.com/lucko/LuckPerms)) you will need Vault and/or PlaceholderAPI.

**Vault** is an API which is able to, for the purposes of this plugin, retrieve group information from a permissions plugin and communicate them to Carbon. It is required to have per-group chat formatting defined, either in the default channel format or in any other channel format. **This plugin requires Vault**.

**PlaceholderAPI** or PAPI is an API which is able to pull information from a variety of places, and Carbon is able to use that information in its chat format. For example, you can use the placeholder for a player's prefix, which it will pull fron Vault, or you can even use a placeholder for the amount of time a player has spent on the server, if you have a PAPI extension for it. **This plugin requires PlaceholderAPI**

## Compatibility

So far, this plugin is only tested on Spigot and Paper 1.16.1. Even so, no versions/server softwares are guaranteed to work, though they may and probably will.