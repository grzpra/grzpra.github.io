---
layout: post
title:  "Radeon RX 9070 vs Radeon RX 7900 XTX"
date:   2026-04-13 10:00:00 +0200
categories: 9070 7900XTX GPU
---
Couple months ago I bought Sapphire Pulse RX 9070 for my spare rig. Before
installing it in the PC it was intended for I run some benchmarks comparing
the card to my 7900 XTX in my main PC.

<!--more-->

## Test Setup

_**Disclaimer:** Please keep in mind that I am not a professional reviewer nor
I aspire to be one. Those are just the the tests I run for my own curiosity.
Testing methodology is most likely flawed._

Hardware configuration:
* Ryzen 9 5950X
* ASRock X570 Taichi (BIOS 5.00 AGESA 1.2.0.7)
* GSkill F4-3200C14D-32GTZKW (2x16GB @ 3733MHz 16-16-16-32 1T GDM On)
* Plextor M5 Pro 256GB
* Noctua NH-D15S
* Seasonic Vertex GX-1000 1000W Gold

GPUs under test:
* PowerColor 7900XTX Red Devil @ 2525/2500 MHz (silent BIOS)
* Sapphire Pulse RX 9070 @ 2520/2518 MHz

Used software versions:

| Software | Version |
|:--------:|:-------:|
| Windows 11 | 25H2 (Memory integrity off) |
| AMD GPU drivers | 25.12.1 |
| AMD chipset drivers | 7.11.26.2142 |
| 3D Mark Time Spy | 1.2 |
| 3D Mark Speed Way | 1.1 |
| Cyberpunk 2077 | 2.31 |
| Shadow of the Tomb Raider | 1.0.1.1 GOG |
| Metro Exodus Enhanced | s04_black_smoke |

## Tests Results

Keep in mind that while the RX 9070 I have used for this comparison runs
with reference clocks as far as I know, used 7900 XTX (PowerColor Red Devil) by
default uses slightly bumped clocks. This might influence the results a bit.
I only benchmarked the cards in 2560x1440 resolution, partially because that is
the resolution I use daily, partially because I think this is the standard those
days. 3DMark tests were run using the default resolution for those benchmarks.

![Time Spy Extreme](/assets/9070_VS_7900XTX/time-spy-extreme.png)
{: style="text-align:center"}

![Speed Way](/assets/9070_VS_7900XTX/speed-way.png)
{: style="text-align:center"}

As expected RX 7900 XTX comes on top. Speed Way is supposed to use some
ray tracing techniques according to its description [^1].

![Cyberpunk 2077](/assets/9070_VS_7900XTX/cp2077.png)
{: style="text-align:center"}

Settings used for Cyberpunk 2077 (integrated benchmark):

| Resolution | 2560x1440 |
| Quick Preset | Ultra/Ray Tracing: Ultra/Ray Tracing: Overdrive |
| Resolution Scaling | off |

RX 9070 catches up to 7900 XTX when ray tracing is enabled and even edges
it out (by tenths of a frame) with path tracing on.

![Shadow of the Tomb Raider](/assets/9070_VS_7900XTX/sotr.png)
{: style="text-align:center"}

Settings used for Shadow of the Tomb Raider (integrated benchmark):

| Resolution | 2560x1440 |
| API | DirectX 12 |
| Vsync | Off |
| Anti-Aliasing | TAA |
| Preset | Highest |
| Ray Traced Shadow Quality | off/Ultra |

![Chernobylite](/assets/9070_VS_7900XTX/chernobylite.png)
{: style="text-align:center"}

Settings used for Chernobylite (integrated benchmark, first scene only):

| Resolution | 2560x1440 |
| Graphics Quality | Ultra |
| VSync | No |
| Framerate Lock | unlimited |
| Ray Tracing | unavailable |
| AMD FSR 1.0 | off |

This game for some reason does not allow enabling Ray Tracing on AMD cards

## Conclusion

![9070_vs_7900XTX](/assets/9070_VS_7900XTX/overview.png)
{: style="text-align:center"}

On average RX 9070 is ~18.3% slower in rasterization and ~11% slower in
ray tracing (not including CP 2077 path tracing result) in 1440p.
Considering I paid for the RX 9070 less than half of what I had paid for the
7900 XTX and the fact that RX 9070 uses significantly less power I would say
that this is a fair trade-off.

Sapphire Pulse RX 9070 is sitting in my rig at my parents place for a few
months now and I must say I am pretty happy with the card. Card is quiet and
seems quite sturdy and actually pretty compact while still offering decent
performance. I really wanted a power efficient card for that PC (that's why
I didn't grab 9070 XT) and 9070 non-XT provided that.

[^1]: [Overview of 3DMark Speed Way benchmark](https://support.benchmarks.ul.com/support/solutions/articles/44002378655-overview-of-3dmark-speed-way-benchmark)
