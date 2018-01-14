# Commands

Arguments in `<angular brackets>` are required; arguments in `[square brackets]` are not.

## Moderation
### Clear
Deletes messages.
##### Aliases
`clear`, `clr`, `cl`, `purge`, `prune`, `wipe`
##### Usage
`clear [number of messages] [mode] [arg]`

`clear` with no arguments is equivalent to `clear 100 channel (current channel)`

There are a number of ways to select messages to delete:

|Mode|Description|Usage|
|:---|----------:|-------|
|channel|Delete message from a specific channel. Defaults to the current channel.|Use a channel mention or channel ID as the argument.|
|user|Delete messages from a specific user. Defaults to the caller.|Use a mention or user ID as the argument.|
|role|Delete messages from all members of a role.|Use a mention or ID as the argument. **There is no default role.**|
|containing|Delete messages containing specific content types or substrings.|Use `image`, `video`, `embed`, `mention`, `tts` or a substring to search for as the argument.|
|regex|Delete messages according to a specific regex pattern.|Use a regex search string in quotes as the argument. Defaults to `"*"`.|

Commands can also be combined by placing them in brackets:
`(channel #general)/(channel #faq)` means *in either #general or #faq*; `(role @Admin)+(role @Streamer)` means *by a member of both the Admin role and the Streamer role*.

###### Examples
|Command|Result|
|:--|--:|
|`clear 200 containing tts`|The last 200 TTS messages are deleted.|
|`purge 40 user`|Your last 40 messages are deleted.|
|`prune (containing tts)+(channel #general)+(user)`|Your last 100 TTS messages in [#general]() are deleted.|
|`cl user 773245987349774819`|The last 100 messages by the user with this ID are deleted.|
