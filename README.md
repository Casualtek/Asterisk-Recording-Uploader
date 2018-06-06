# Asterisk Recording Uploader

Simple Python __script__ to upload a new Asterisk recording to DropBox, and notify via Slack
This sript does work with the API v2.

Save your _ACCESS TOKEN_ in a environment variables. The access token can be obtained after you have created your application in the follow <a href="https://www.dropbox.com/developers">link</a>.

Open the script and replace ```<ACCESS_TOKEN_DROPBOX>``` with your actual access token.

install DropBox, using:

```
pip install dropbox
```

Also replace ```<WEBHOOK_URL_SLACK>``` with the actual incoming webhook URL of your Slack application.
More on that can be found <a href="https://api.slack.com/incoming-webhooks">here</a>.

Replace ```<USER_SLACK>``` with the identifier of the Slack user to be notified.
Replace ```<BOT_SLACK>``` with the identifier of the channel used by your application to interact with Slack users.

## Usage

The script is intented to be executed as an AGI script right at hangup.
Here is a example of macro for the extensions plan that will thus call the uploader script.

```
[macro-hangupcall]
exten => s,1,AGI(dropbox_uploader.agi,${ASTSPOOLDIR}/monitor/${YEAR}/${MONTH}/${DAY}/${CDR(recordingfile)},/${CDR(recordingfile)})
exten => s,n,Hangup
exten => s,n,MacroExit()

```

### Based on the work of @eduardo_gpg

The original work this script derives from can be found <a href="https://github.com/eduardogpg/dropbox_uploader">here</a>.

License
----

MIT
