# icfp2020-captions

The master copy of each file is the `.ass` file, *do not edit the .srt* as your edits will get overwritten

To convert `sessionN.ass` file to `sessionN.srt`:
```
ffmpeg -i sessionN.ass -f srt - | sed -e 's|</*font[^>]*>||g' > sessionN.srt
```

The `.srt` files from AI Media have DOS line endings, the ones produced by `ffmpeg` have Unix, so the first time you check in an `.srt` file:
```
dos2unix */*.srt
```
