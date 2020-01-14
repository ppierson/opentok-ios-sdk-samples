Bug Description:  
The `publisher:streamCreated:` callback is never fired when the app is in the background.

This bug appears when running on a physical iPhone (iPhone X used for this example, we see the same on all other phones as well).
It only occurs when the `Audio` background mode is enabled and another Audio file is playing using AVPlayer at the same time.
We experienced this issue because we play waiting music in our app when waiting for other users to connect to the OpenTok session.

Steps to reproduce bug:
- Set API Key, SessionID and Token.
- Run app on a device.
- Minimize the app as soon as it launches.
- Notice the `"Will start publisher"` log in the terminal.
- Notice that the `"Error publishing!"` and `"Publishing"` logs are never called.
- Bring app to foreground, neither log is called.
