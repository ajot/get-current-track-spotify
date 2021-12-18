# Get Current Track from Spotify using AppleScript
Here's the Apple script that will get the track information from Spotify for the current track. Once you have this, you just need a way to print the result somewhere. I use the [Text Expander](https://textexpander.com) app on the Mac to insert text snippets with simple keyboard shortcuts.

```applescript
if application "Spotify" is running then
    tell application "Spotify"
        if (get player state) is playing then
            set appProperties to properties
            set currentTrack to current track
            set songName to (get name of currentTrack)
            set songArtist to (get artist of currentTrack)
            set returnString to "\"" & songName & "\"" & " by " & "\"" & songArtist & "\""
            return returnString

        end if
        return (get player state)
    end tell
else
    return "Spotify is not running"
end if
```

### Add the Script to Text Expander
Then you just add that to TextExpander.
Set "Content" to "AppleScript", and paste the script above.
Assign a keyboard shortcut you would like. I used "song;" (with a semi-colon).
That's it. Now, when you type that combination anywhere on your Mac, it will replace that with the name of the song currently playing.

![](https://ajot.me/content/images/size/w1000/2021/12/spotify-text-expander.png)