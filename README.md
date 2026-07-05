# vmi — Verify Media Integrity

I couldn't find any decent options online, so I made my own.

**vmi** is a file integrity checker supporting multiple file types (image,
video, audio, archives, formatted documents (PDFs), ...).

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

> [!note] Disclaimer
> Unrecognized file types are scanned by default with no given file type.
> This but this will flag as *corrupt* any file it fails to scan.
