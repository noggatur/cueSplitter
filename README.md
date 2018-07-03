# Cue Splitter

Splits a `flac-cue` album into separate `flac` files.


## Install

Install required packages.
```sh
brew install cuetools flac ffmpeg shntool
```

Allow user to launch our bash scripts.
```sh
chmod +x ./run ./cuetag ./renamer
```


## Run

```sh
./run path/to/folder/containing/cue-flac-album
```


## Automator

For creating a service in Automator (AppleScript)

```bash
cd /Users/igor/Repos/cueSplitter/
sh ./run "$1"
say "Ready!"
```

or

```applescript
on run {input, parameters}
  set bashScript to "echo '" & (input as string) & "' | tr ':' '/' | cut -d '/' -f 2-"
  -- display dialog bashScript

  set pathToAlbum to (do shell script bashScript)
  -- display dialog pathToAlbum

  tell application "Terminal"
    do script "cd /Users/user/path/to/script; sh ./run '/" & pathToAlbum & "'; say Ready!"
    close
  end tell

  return input
end run
```


## Source scripts

- https://coderwall.com/p/6ydyoq/how-to-split-flac-files-by-cue-and-convert-to-alac-on-mac-os-x
- https://github.com/gumayunov/split-cue/blob/master/cuetag