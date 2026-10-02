## Pads

```javascript
// DRONE Pad by YouTube @duckattack-sound
$drone:
  s("tri").seg(8)
    .fm(sine.range(1,8).slow(4)).fmh(slider(.5,0,8))
    .adsr("0.2:0.1:0.5:1")
    .room("1:5")
    .pan(perlin.slow(4))
    .postgain(.8)
```

## Drums
