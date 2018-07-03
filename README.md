# Cue Splitter

Splits a `flac-cue` album into separate `flac` files.


## Install

Install required packages.
```sh
brew install cuetools shntool flac
```

Allow user to launch our bash script.
```sh
chmod +x ./run
```


## Run

```sh
./run path/to/folder/containing/cue-flac-album
```


## Automator

For creating a service in Automator (AppleScript)

```applescript
on run {input, parameters}
  set bashScript to "echo '" & (input as string) & "' | tr ':' '/' | cut -d '/' -f 2-"
  -- display dialog bashScript

  set pathToAlbum to (do shell script bashScript)
  -- display dialog pathToAlbum

  tell application "Terminal"
    do script "cd /Users/igor/Repos/cueSplitter/; python ./run '/" & pathToAlbum & "'; say Ready; exit"
    close
  end tell

  return input
end run
```


## Source scripts

- https://github.com/trustmaster/imgsplit
- https://coderwall.com/p/6ydyoq/how-to-split-flac-files-by-cue-and-convert-to-alac-on-mac-os-x
- https://github.com/gumayunov/split-cue/blob/master/cuetag