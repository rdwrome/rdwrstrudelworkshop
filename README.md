# WIFI
## Royalston Library
## psnewton

# https://bit.ly/rachellivecodestrudel

### laptop, browser, headphones check

### introductions!
- name, hometown, best thing you ate over the holidays

# rdwr [strudel](https://strudel.cc/)
- based on work by [chris peck](https://learningmusic.ableton.com/  ) and [jade rose](https://strudel.cc/workshop/first-sounds/)

## words to live by
- amplitude: strength of a sound wave (i.e. "loudness")
- pitch: lowest frequency of a complex, periodic sound wave (i.e. what you sing when you're trying to sing "with" something)
- timbre: higher frequencies in a complex, periodic sound wave (i.e. how you can tell your voice is different than the thing you're trying to sing with)
- synthesis = process of making something 'synthetic' (human-made) with a 'synthesizer'
- sequence = a repeating pattern where order matters (typically with synthesizers they're 8 or 16 steps against a computer clock)
- source: a synthesized sound or sequence you are going to change into something else
- modifier: something you're using to change the amplitude, pitch, or timbre of synthesized sound or a pattern
- patch: how parts of a synthesizer are connected in terms of source and modifiers

## Strudel is based on [TidalCycles](https://tidalcycles.org/)
- [Everything is pattern-based](https://tidalcycles.org/docs/reference/cycles)
- Uses JavaScript in the browser (so you don't have to download anything!)
- Not quite as powerful as TidalCycles...

## starter pattern commands and syntax
`s` = sound

`" "` = what to fit inside one cycle

`~` = silence

`!` = repeat

**starter examples**

`s ("bd")`

`s ("bd hh")`

`s ("bd ~ hh")`

`s ("bd ~ hh!2")`

**everybody now!**

## [Strudel Interface](https://strudel.cc/)
- console
- sounds
- reference

## more advanced commands and syntax

`[]` = nest these within one pulse of the cycle

`,` = layer these atop one another within one cycle

`[ | ]` = randomly choose sample from this list per cycle

`?` = randomly silence

`( , )` = spread this many pulses over this many pulses per cycle

**more examples**

`s "(bd ~ [hh!2]")`

`s ("bd, ~ hh")`

`s ("[bd | hh | sd]!4")`

`s ("hh!16?")`

`s ("bd(7,12)")`

**everybody now!**

## stack

`stack (s (" "),
s (" "))`

**stack of example**
- you gotta watch for what the sound source is

`stack(
  "[bd ~ ~ bd] [~ ~ ~ bd] [~ bd bd ~] [~ ~ ~ ~] ",
  "[~ ~ ~ ~] [sd ~ ~ ~] [~ ~ ~ ~] [sd ~ ~ ~] ",
  "[hh ~ hh ~] [hh ~ hh ~] [hh ~ ~ ~] [hh ~ hh ~] ",
  "[~ ~ ~ ~] [ho ~ ~ ~] [~ ~ ho ~] [~ ~ ~ ~] ",
).s()`


**everybody now!**

## [MIDI NOTES](https://inspiredacoustics.com/en/MIDI_note_numbers_and_center_frequencies)

## noted (pitch sources)

- define by midi note

`note ("48").sound("sawtooth")`

- or note name

`note ("c").sound("sawtooth")`

- sequence away

`note ("c d e").sound("sawtooth")`

- sequence over multiple cycles

`note ("[c d e]/4").sound("sawtooth")`

- play one per cycle

`note ("c <c d e> e").sound("sawtooth")`

**everybody now!**

## effected (timbre modifiers)

- low pass filter

`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>")`

- 'gain'

`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>").gain(1.2).vowel("<a e i o u>")`

- 'vowel'

`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>").vowel("<a e i o u>")`

**everybody now!**

## time (clock sources and modifiers)

- cps

`s("<bd sd>,hh*2").cpm(140)`

- fast

`s("bd hh sd hh").fast(2) `

- slow

`s("bd hh sd hh").slow(2) `

**everybody now!**

## Lab time

## Sharing is Caring
