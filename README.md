[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
# Emote Widget

## How to Use

### For starters...

This widget is driven by two pieces of information:
#### Client ID
[Twitch Docs](https://dev.twitch.tv/docs/v5#getting-a-client-id)  
This is used for twitch api authentication. Creating one is simple and is used for non-authenticating requests when not accompanied with an OAuth token. It will look something like this `gn4m6kqja6gkcgt24z0pbt823rurvq`.

To obtain your own client id, log into the [twitch developers webpage](https://dev.twitch.tv/login). This Twitch's developer page and uses your Twitch username and password.

Once logged in, navigate to the [Application Dashboard](https://dev.twitch.tv/console/apps)

- Register a new application. Use the below values:
    - Name: This name can be whatever you want as long as Twitch is not included **AND** is unique.
    - OAuth Redirect URLs: localhost
    - Category: Browser Extension
    - Confirm you are not a robot.
- Click Create

Click into the newly created application. Find the **Client ID** near the bottom. This is not a secret value

Copy the **Client ID** and replace the value on line 6 in **main.js**

#### Channel Name
    - The name of the channel you want to pull emotes from.
    - In this example twitch channel https://www.twitch.tv/itsatreee, itsatreee is the channel name.