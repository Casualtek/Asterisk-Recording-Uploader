# Asterisk Recording Uploader

Simple Python __script__ to upload a new Asterisk recording to DropBox, and notify via Slack
This sript does work with the API v2.

Save your _ACCESS TOKEN_ in a environment variables. The access token can be obtained after you have created your application in the follow <a href="https://www.dropbox.com/developers">link</a>.

Open the script and replace ```<ACCESS_TOKEN_DROPBOX>```for the name of your environment variables.

install DropBox, using:

```
pip install dropbox
```

## Usage

```
python dropbox_uploader.py path_file
```

```
python dropbox_uploader.py path_file dest_path
```

> If we dont especify the dest_path the default will be the same route (path_file)

### Based on the work of @eduardo_gpg

The original work this script derives from can be found <a href="https://github.com/eduardogpg/dropbox_uploader">here</a>.

License
----

MIT
