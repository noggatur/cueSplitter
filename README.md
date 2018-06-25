# Cue Splitter

Splits a `flac-cue` album into separate `flac` files.


## Procedure

Install required packages.
```sh
brew install cuetools flac ffmpeg shntool
```

Split `flac` file by `cue`.
```sh
shnsplit -o flac -f file.cue file.flac
```

Allow user to launch our bash scripts.
```sh
chmod +x ./cuetag ./renamer
```

Fill meta-info for the resulting flac files.
```sh
./cuetag file.cue split-track*.flac
```

Rename all the files to their original names.
```sh
./renamer
```


## Source scripts

- https://coderwall.com/p/6ydyoq/how-to-split-flac-files-by-cue-and-convert-to-alac-on-mac-os-x
- https://github.com/gumayunov/split-cue/blob/master/cuetag