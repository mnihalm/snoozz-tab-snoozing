# Privacy

#### Permissions

The extension requires the following permissions:
- **alarms** - To schedule when tabs should wake up
- **contextMenus** - To add right-click menu options for snoozing
- **idle** - To detect when your device wakes from sleep
- **notifications** - To notify you when tabs wake up
- **storage** - To save your snoozed tabs and settings
- **tabs** - To read and close tabs when snoozing

#### Data Collection
Snoozz collects a minimal amount of anonymous tracking data and sends it to an [open source server](https://github.com/rohanb10/snoozz-stats).

The few lines of code used to send this data can be found in the [`./scripts/poll.js`](https://github.com/rohanb10/snoozz-tab-snoozing/blob/master/scripts/poll.js). The data is initially sent from the `displayPreviewAnimation(...)` function in [`./scripts/popup.js`](https://github.com/rohanb10/snoozz-tab-snoozing/blob/master/scripts/popup.js) to [`./scripts/background.js`](https://github.com/rohanb10/snoozz-tab-snoozing/blob/master/scripts/background.js) using the WebExtension Runtime API `runtime.sendMessage(...)`. It is processed in the background so that the speed of the extension is not compromised in any way

No other data is collected. Your snoozed urls, geolocations, ip addresses and even languages have never, and will never be used in any way.

You can open your Network tab in your Browser inspector and see exactly what is being sent to the server. If you snooze a tab for monday at 4:15pm, the string `monday.1615` will be sent over to the server. That's it.

You may turn this off on the settings page of your extension.
