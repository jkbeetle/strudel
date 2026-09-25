# Strudel Cheatsheet

## General
- Ctrl-Enter : Play
- Ctrl-. : Stop
- Ctrl-/ : Comment
- setcpm : set Cycles per Minute

## Mini Notation
- Division / : play over several cycles
- Multiplication * 
- <> : Sequence length based on events
- [] : Nesting, SubSequencing
- \- or ~ : Rest
- , : play at same time
- @ : Elongation (change temporal weight)
- ! : Repeat without speeding up
- () : [Euclidian Rythm](https://en.wikipedia.org/wiki/Euclidean_rhythm) (b,s,o)
  - b: Number of Beats played
  - s : Numbr of Segments distributed over
  - o : optional offset
- ply : multiplies each event
- use backticks ` for multiple line notation

## Notes and Sounds
- note()/n(), names, [MIDI](https://inspiredacoustics.com/en/MIDI_note_numbers_and_center_frequencies) numbers
- freq()
- sound()/s() bd, hh, 
- combine: n().s()
- \$: parallel threads, _$: pause thread, S$: Mute others
- add : adds number to note
- scale : turn numbers into scale note

## Samples
- Defaults
  - bd : Bass drum, Kick drum	
  - sd : Snare drum	
  - rim : Rimshot	
  - cp : Clap	
  - hh : Closed hi-hat	
  - oh : Open hi-hat	
  - cr : Crash	
  - rd : Ride	
  - sh : Shakers (and maracas, cabasas, etc)	
  - ht : High tom	
  - mt : Medium tom	
  - lt : Low tom	
  - cb : Cowbell	
  - tb : Tambourine	
  - perc : Other percussions	
  - misc : Miscellaneous samples	
  - fx : Effects	
- bank() - Load bank, can contain Mini Notation
- : : access sound s("bd:1"), s("bd").n("1")
- use note for pitch samples
- speed() : Change speed/pitch of sample, negatives for backwards
- clip() : Clip Samples, default 1
- begin() : Skips beginning of sample 0 nothing, 1 full
- end() : Cuts off end of sample 0 nothing (full sample), 1 full
- cut() : cuts sample as soon other one in group is playing
- loopAt() : change speed of sample so it loops after cycles
- chop() : Chop up samples
- rev() : play reversed (same as speed(-1))
- samples() to define own samples with reference to a GitHub Repo
```javascript
samples({
  guitar: [
    'samples/guitar/guitar_0.wav', 
    'samples/guitar/guitar_1.wav', 
    'samples/guitar/guitar_2.wav', 
    'samples/guitar/guitar_3.wav', 
    'samples/guitar/guitar_4.wav'
  ]
}, 'github:jarmitage/jarmitage.github.io/master/');
s("[guitar:0 guitar:1 guitar:2 guitar:3 guitar:4]/5")
```
- import samples from freesound or generate text2speech with [Shabda](https://shabda.ndre.gr/)

## Effects
- .lpf() - low pass filter, value, pattern possible
- .vowel()
- .gain() - make rythm interesting
- adsr("a:d:s:r") - combine attack(), decay(), sustain() and release()
- delay("v:t:f") - volume, delay time and feedback
- room() - reverb effect
- hush() - silence patter
- pan()
- use modulation signals sine, saw, swaure, tri rand, perlin
  - modify with .range(min,max)
- off() 

## Others
- apply effect to everything
```javascript
all( x => (x.spectrum()))
```
