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

## Example output

Running this in a DCIM folder to successfully identify all video file stubs:

```
$ vmi
Checking dir '.' ...

FAIL : ./Camera/VID_20260604_202238.mp4.tmp
       ./Camera/VID_20260604_202238.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x563f71dc8780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260604_202238.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260605_202136.mp4.tmp
       ./Camera/VID_20260605_202136.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x561599822780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260605_202136.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260105_200303.mp4.tmp
       ./Camera/VID_20260105_200303.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x561794749780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260105_200303.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20251215_011241.mp4.tmp
       ./Camera/VID_20251215_011241.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x5586a8a35780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20251215_011241.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260104_204754.mp4.tmp
       ./Camera/VID_20260104_204754.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x564e0eb8c780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260104_204754.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260404_170819.mp4.tmp
       ./Camera/VID_20260404_170819.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x562de4196780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260404_170819.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260404_171053.mp4.tmp
       ./Camera/VID_20260404_171053.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x56492d30c780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260404_171053.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260407_225402.mp4.tmp
       ./Camera/VID_20260407_225402.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x55cddecb0780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260407_225402.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260413_010440.mp4.tmp
       ./Camera/VID_20260413_010440.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x557d1236a780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260413_010440.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260420_230504.mp4.tmp
       ./Camera/VID_20260420_230504.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x561512171780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260420_230504.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260501_151538.mp4.tmp
       ./Camera/VID_20260501_151538.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x562e70124780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260501_151538.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260502_202040.mp4.tmp
       ./Camera/VID_20260502_202040.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x55e32c999780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260502_202040.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260517_210845.mp4.tmp
       ./Camera/VID_20260517_210845.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x55ff5a2a3780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260517_210845.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260518_084414.mp4.tmp
       ./Camera/VID_20260518_084414.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x563eaa3e5780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260518_084414.mp4.tmp.
       Error opening input files: Invalid data found when processing input
FAIL : ./Camera/VID_20260602_011500.mp4.tmp
       ./Camera/VID_20260602_011500.mp4.tmp: Invalid data found when processing input
       [in#0 @ 0x55c50c9c5780] Error opening input: Invalid data found when processing input
       Error opening input file ./Camera/VID_20260602_011500.mp4.tmp.
       Error opening input files: Invalid data found when processing input
----------------------------------------
Checked: 13358  OK: 13343  FAIL: 15  SKIP: 0

Corrupt files:
  ./Camera/VID_20260604_202238.mp4.tmp
  ./Camera/VID_20260605_202136.mp4.tmp
  ./Camera/VID_20260105_200303.mp4.tmp
  ./Camera/VID_20251215_011241.mp4.tmp
  ./Camera/VID_20260104_204754.mp4.tmp
  ./Camera/VID_20260404_170819.mp4.tmp
  ./Camera/VID_20260404_171053.mp4.tmp
  ./Camera/VID_20260407_225402.mp4.tmp
  ./Camera/VID_20260413_010440.mp4.tmp
  ./Camera/VID_20260420_230504.mp4.tmp
  ./Camera/VID_20260501_151538.mp4.tmp
  ./Camera/VID_20260502_202040.mp4.tmp
  ./Camera/VID_20260517_210845.mp4.tmp
  ./Camera/VID_20260518_084414.mp4.tmp
  ./Camera/VID_20260602_011500.mp4.tmp
```

> Add the `-v` flag if you want to see more than just failed checks.

## Todo

- Environment variable for files/file types to ignore
- Option to ignore single files/directories
- *Probe* (`ffprobe`) option to only check header metadata (faster)
