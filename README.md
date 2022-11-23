# domekbajeczka.pl

## Images

Cheet sheet of 16:9 resolutions:
```
2160p: 3840×2160
1440p: 2560×1440
1080p: 1920×1080
720p: 1280×720
480p: 854×480
360p: 640×360
240p: 426×24
```
4:3:
```
640 ✕ 480
800 ✕ 600
1024 ✕ 768
1152 ✕ 864
1280 ✕ 960
1600 ✕ 1200
1920 ✕ 1440
2048 ✕ 1536
3840 ✕ 2889
4096 ✕ 3072
```

Image pipeline:
- get the original image. If it's not absurdly big (in terms of pixel count), leave size as is - otherwise resize to something sane, like 3840 above
  - psst: check resolution with `magick identify image.jpg`
- run `jpegoptim -m 90 image.jpg` on it
- add to `media/`
- do stuff with hugo's processing:
  - resize stuff
  - stick to webp cause it's almost always better looking at same size
  - `q40` is suprisingly good
