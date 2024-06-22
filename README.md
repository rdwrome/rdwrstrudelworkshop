# rdwr [strudel](https://strudel.cc/)
- based on work by [chris peck](https://learningmusic.ableton.com/  ) and [jade rose](https://strudel.cc/workshop/first-sounds/)

## words to live by
- amplitude: strength of a sound wave (i.e. "loudness")
- pitch: fundamental frequency of a periodic sound wave (i.e. what you sing when you're trying to sing with something)
- timbre: frequencies above the fundamental in a complex sound wave (i.e. how you can tell your voice is different than the thing you're trying to sing with)
- synthesis source: a sound you're changing
- synthesis modifier: something you're using to change a sound
- synthesis patch: how parts of a synthesizer are connected (typically used to describe a timbre or sequence, see below)
- synthesis sequence: a pattern of source or modifier information (typically they're 8 or 18 steps against a computer clock)

## Strudel is based on [TidalCycles](https://tidalcycles.org/)
- Everything is pattern-based
  - [NOT BPM!](https://tidalcycles.org/docs/reference/cycles)
  - patterned sequences against a computer clock
- Uses JavaScript in the browser (so you don't have to download anything!)
- Not quite as powerful as TidalCycles

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

**stack of examples**

`stack (
s ("bd(7,12)"),
s ("hh!16?")
)`

**everybody now!**

## noted
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

## effected
-low pass filter
`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>")`
-'gain'
`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>").gain(1.2).vowel("<a e i o u>")`
-'vowel'
`note ("c <c d e> e").sound("sawtooth").lpf("<400 500>").vowel("<a e i o u>")`
