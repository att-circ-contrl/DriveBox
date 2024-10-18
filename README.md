# Triad Drive Motor Controller

## Overview

The Triad drive and its variants are driven by miniature motors from Namiki.
These take +/-3V sine waves with three phases and a common return
(probably Y-topology, but not ruling out delta-plus-ground).

The controller boxes we have are ones that we can't get more of, and the
cabling is unreliable, so I started designing a replacement.

**This was never finished.** A prototype of the front panel was designed
but the shield wasn't.

The tenatative plan was to use a 5V supply and use buffer amplifiers to
produce 0V, 2.5V, and 5V. The 2.5V line would be the common return, and
the motors would be driven with square waves at +/-2.5V.

There's no guarantee that this would have worked; the motors sometimes got
stuck even at 3V. But there's high confidence that it would be _safe_ to use
with the motors (de-rated voltage).

It's questionable if the AD86xx amplifiers would have been able to source
and sink enough current.


## Notes

The original plan was to have separate analog and digital headers, to avoid
injecting digital noise into the motor cabling (which is right next to ephys
cabling).

The revised plan (at least for the prototype) was to put the analog
circuitry on the mainboard (Arduino shield), and have analog and control
signals both on the microcontroller header.

The microcontroller header therefore has two different use-cases for the
same pinout. In digital mode, per the schematic, the "motor drive phase"
signals are driven at TTL voltages and the "Com/NC" signal is disconnected
(or better yet, grounded). In analog mode, the analog buffers are before
that header, and the "motor drive phase" signals are fed directly to the
motors, with "Com/NC" being the common return (shared between all motors,
which may cause problems with ground loops).


_(This is the end of the file.)_
