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

## Arrangements
```javascript
setcpm(110/4)

const sc="E3:major"

const arp = n("[-1 0 4 2]!3 [-1 0 4@2]".add(14)).slow(2)
const ostenato = n("~ <2 -2 2>@2 3 4@4")


const bass = n("3 [~ 3@7] 0 1".add("-7")).slow(4)
const bass_end = n("0 1".add("-7")).slow(2)

const IV = "-4, 0, 3, 5, 7"
const VI = "-2, 0, 2, 5, 7"
const I = "0, 2, 4"

const intro=n(cat(IV, silence, VI, stack(I, "1 2".add(7))))
const chorus1 = stack(arp, ostenato, bass.reset("x"))


$: arrange(
  [8, chorus1],
  //[2, chorus1_end],
  [8, intro]  
)
  .scale(sc)
  .s("piano")
  .velocity(rand.range(0.7,1)) //humanize
  .room(1)
  .delay(.2)

```
