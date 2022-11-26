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
### 4k resolutions:
| Format      | Resolution         |
|-------------|--------------------|
| 3840 x 1080 | 3.55∶1 (32∶9)      |
| 3840 x 1600 | 2.40∶1 (12∶5)      |
| 3840 x 2160 | 1.77∶1 (16∶9)      |
| 3840 x 2400 | 1.60∶1 (16∶10)     |
| 3996 x 2160 | 1.85∶1 (≈37∶20)    |
| 4096 x 1716 | ≈2.39∶1 (1024∶429) |
| 4096 x 2160 | ≈1.90∶1 (256∶135)  |
| 4096 x 2304 | 1.77∶1 (16∶9)      |
| 4096 x 2560 | 1.60∶1 (16∶10)     |
| 4096 x 3072 | 1.33∶1 (4∶3)       |

Image pipeline:
- get the original image. As original as it can be. Pipe it through AI resolution enlarger - either cloud one or Upscayl! on pc (Upscayl! is better)
- convert it's size back to 4K or smth like that
  - psst: check resolution with `magick identify image.jpg`
- run `jpegoptim -m 90 image.jpg` on it
  - you can run it once, or until it stops optimizing, i don't see big different - i will stick to once
  - stick to jpg because the output will have a bit off colors if you use webp at this stage
- add to `media/`
- do stuff with hugo's processing:
  - resize stuff
  - stick to webp cause it's almost always better looking at same size
  - `q40` is suprisingly good
