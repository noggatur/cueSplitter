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

For creating a service in Automator
```bash
cd /absolute/path/to/this/script/folder/
sh ./run "$1"
say "Ready!"
```


## Source scripts

- https://coderwall.com/p/6ydyoq/how-to-split-flac-files-by-cue-and-convert-to-alac-on-mac-os-x
- https://github.com/gumayunov/split-cue/blob/master/cuetag