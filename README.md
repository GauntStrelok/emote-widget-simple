[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
# Emote Widget

![test](https://static-cdn.jtvnw.net/emoticons/v1/300929371/2.0)

## How to Use

### For starters...

This widget is driven by two pieces of information: `clientId` and `channel name`.

#### Client ID
[Twitch Docs](https://dev.twitch.tv/docs/v5#getting-a-client-id)  
This is used for twitch api authentication. Creating one is simple and is used for non-authenticating requests when not accompanied with an OAuth token. It will look something like this `gn4m6kqja6gkcgt24z0pbt823rurvq`.

To obtain your own client id, log into the [twitch developers webpage](https://dev.twitch.tv/login). This is Twitch's developer page and uses your Twitch username and password to authenticate.

Once logged in, navigate to the [Application Dashboard](https://dev.twitch.tv/console/apps)

- Register a new application. Use the below values:
    - Name: This name can be whatever you want as long as Twitch is not included **AND** is unique.
    - OAuth Redirect URLs: **localhost**
    - Category: **Browser Extension**
    - **Confirm you are not a robot.**
- Click Create

Click into the newly created application. Find the **Client ID** near the bottom. This is not a secret value but is a unique identifier for the application.

Copy the **Client ID** and replace the value on line 2 in **main.js**. (Make sure the client id is between the tick marks; 'clientId')
- `const clientId = 'gn4m6kqja6gkcgt24z0pbt823rurvq'`

#### Channel Name

The name of the channel you want to pull emotes from. In this example twitch channel https://www.twitch.tv/itsatreee, `itsatreee` is the channel name.

### Configuration

#### URL Parameters

Param | Default Value | Description
--- | --- | ---
channel (Required) | itsatreee | The channel whose emtoes to display
clientId (Required) |  | The client id of your Twitch application created above
showTwitch | true | Determines if Twitch emotes are added to the random pool of visible emotes.
showBttv | true | Determines if Bttv emotes are added to the random pool of visible emotes.
totalEmotes | 100 | Determines the total emotes create in one iteration.
secondsToRain | 10 | Determines for how long emotes will be created.
secondsToWaitForRain | 23 | How long to wait to start raining emotes again after they are stopped.
numTimesToRepeat | 1 | The number of times to repeat. Use -1 for continuous raining emotes!!

`Examples:`
- file:///C:/path/to/emote-widget-simple/screen-display.html?channel=itsatreee&numTimesToRepeat=1`
  - Show Twitch and Bttv emotes from ItsATreee's channel
  - Only rain emotes once.

- file:///C:/path/to/emote-widget-simple/screen-display.html?showTwitch=true&showBttv=false&totalEmotes=100&secondsToRain=10&secondsToWaitForRain=23&channel=itsatreee&numTimesToRepeat=1`
  - Shows Twitch Emotes
  - Hides Bttv Emotes
  - Total Emotes shown will be 100
  - Emotes will be created at the top of the screen for 10 seconds
  - Emotes will start raining again after 23 seconds total
  - Show emotes from ItsATreee's channel
  - Only rain emotes once.

- file:///C:/path/to/emote-widget-simple/screen-display.html?showTwitch=false&showBttv=true&totalEmotes=250&secondsToRain=15&secondsToWaitForRain=35&channel=itsatreee&numTimesToRepeat=-1`
  - Hides Twitch Emotes
  - Shows Bttv Emotes
  - Total Emotes shown will be 250
  - Emotes will be created at the top of the screen for 15 seconds
  - Emotes will start raining again after 35 seconds total
  - Show emotes from ItsATreee's channel
  - Emotes will rain continuously
