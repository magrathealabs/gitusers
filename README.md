# Generate MP4

1. Clone this repo into the git repository.

2. Run:
```sh
gource --key --seconds-per-day 0.1 --hide filenames --highlight-users --user-image-dir gitusers --user-scale 5 --background-image "gitusers/background.jpg" --title "Rôgga Sales Force" --auto-skip-seconds 1 --padding 1.3 -1280x720 -o - | ffmpeg -y -r 60 -f image2pipe -vcodec ppm -i - -vcodec libx264 -preset ultrafast -pix_fmt yuv420p -crf 1 -threads 0 -bf 0 input.mp4
```

OR (25FPS):
```sh
gource --key --seconds-per-day 0.1 --hide filenames --highlight-users --user-image-dir gitusers --user-scale 2 --background-image "gitusers/background.jpg" --title "Extractor Workers" --auto-skip-seconds 1 -r 25 --padding 1.3 -1280x720 -o - | ffmpeg -y -r 25 -f image2pipe -vcodec ppm -i - -vcodec libx264 -preset ultrafast -pix_fmt yuv420p -crf 1 -threads 0 -bf 0 input.mp4
```

# Reduce .MP4 size converting to .h264

```sh
ffmpeg -i input.mp4 -an -vcodec libx264 -crf 23 outfile.h264
```

or

```sh
ffmpeg -i input.mp4 -an -vcodec libx264 outfile.h264
```

In some cases, ffmpeg cut frames.
In this case, use Blender for this convertion.
