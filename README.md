# vmi — Verify Media Integrity

**vmi** is a file integrity checker supporting image, audio, video, archive
and formatted document (PDF) file types.

I couldn't find a decent option anywhere, so I made my own.

## Install

```
chmod +x vmi
cp vmi /usr/local/bin/
```

## Dependencies

Optional dependencies for each file type:

| type       | tool     |
|------------|----------|
| media      | `ffmpeg` |
| pdf        | `qpdf`   |
| zip        | `unzip`  |
| tar/tgz    | `tar`    |
| gz         | `gzip`   |
| bz2        | `bzip2`  |
| 7z         | `7z`     |
| rar        | `unrar`  |

## Usage

```
vmi --help
```

## Quickstart

To just wildly check recursively all (non-hidden) files in the working
directory run:

```
vmi
```

Unrecognized file types are scanned by default when no file type is specified,
which will flag as *corrupt* any file **vmi** fails to decode (such as `.txt`
files). To prevent this you can ignore (`--skip=...`) any specific file
types you don't want to be verified.

## Todo

- read from env vars files/file types to ignore
- ignoring single files/directories
- add *probe* (`ffprobe`) option to only check header metadata (faster)
