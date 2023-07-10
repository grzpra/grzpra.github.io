---
layout: post
title:  "PowerColor 7900XTX Red Devil: issues with stock TIM application"
date:   2023-07-10 14:00:00 +0200
categories: GPU PowerColor 7900XTX 
---
I purchased PowerColor 7900XTX in January 2023. Card is a performance beast,
however PowerColor might have messed up the paste application on at least
early batches.

<!--more-->

## Issue description

Since early 2023 there was a lot of reports of Red Devil cards having very
high delta between GPU temperature and Hot Spot temperature (around 30-35 K) [^1]
[^2]. Unfortunately, my GPU was also affected by this. I must admit I did not
even realize that this is the case in the beginning. When I got the card
I tested it quickly with Furmark and the delta between GPU and Hot Spot was perfectly
acceptable 20 K. However I did not realize that, when Furmark is running, GPU
goes into some kind of throttle mode (GPU Clock is under 2 GHz!), so it does not
show full picture. Few weeks later I saw Hot Spot hitting 100 °C when playing
DOOM Eternel and I knew something is not OK.

I have contacted PowerColor, but they claimed that such big difference between
temps is normal. Well, I did not agree and was considering repasting the card
myself (that would mean voiding the warranty on over 1k EUR GPU, which I was not
keen on). Luckily around that time Igor's Lab did a great job describing the issue
in detail [^3]. This actually forced PowerColor to react, after couple more mails
they accepted the fact that temps on my card are not OK and I RMAed the card
(I must add that the RMA process was pretty quick at least!).

## Measurements

Before sending card for RMA among I logged all GPU parameters during Fire Strike
Ultra and Time Spy Extreme Stress Tests. Stress Tests were set to default of 20
loops each. Ambient temperature in both cases was almost identical (if I can
trust my super cheap kitchen thermometer). Card was warmed up before the runs and
"OC Bios" was selected in both cases.

# Test setup

* Ryzen 9 3900X
* ASRock X570 Taichi
* GSkill F4-3200C14D-32GTZKW (2x16GB B-Die)
* Samsung 980Pro 1TB (system)
* PowerColor 7900XTX Red Devil

# FireStrike Ultra Stress Test

| Parameter (average value) | before RMA | after RMA |
|:--------:|:-------:|:-------:|
| GPU temp | 67.3 °C | 74.6 °C |
| Hot Spot | 99.3 °C | 95.8 °C |
| GPU clock | 2381 MHz | 2426 MHz |
| Fan speed | 1337 rpm | 1286 rpm |

![Temperatures during Fire Strike Ultra](/assets/PowerColor_7900XTX_TIM/firestrike_ultra.png)
{: style="text-align:center"}

# Time Spy Extreme Stress Test

| Parameter (average value) | before RMA | after RMA |
|:--------:|:-------:|:-------:|
| GPU temp | 67.5 °C | 74.9 °C |
| Hot Spot | 97.7 °C | 95.2 °C |
| GPU clock | 2466 MHz | 2495 MHz |
| Fan speed | 1313 rpm | 1276 rpm |

![Temperatures during Time Spy Extreme](/assets/PowerColor_7900XTX_TIM/timespy_extreme.png)
{: style="text-align:center"\}

## Conclusion

From the numbers above we can see that RMA/repasting the card definitely did
something. While the Hot Spot temps did not drop significantly, card is boosting
higher, so that is something. I am still not 100% happy, I did not expect such
expensive GPU to have a TIM application issue in 2023, this is unacceptable in my
opinion. I will think twice before purchasing something from PowerColor again.

The thing that surprises me most in this story is that, there was almost zero
reaction on this obvious issue from most of the HW news sites. Only smaller sites
linked Igor's article on main pages, in a world where every slip up from
manufacturer is immediately top news everywhere, this is really unexpected.

[^1]: [Powercolor Red Devil 7900 xtx temperature fixes](https://www.reddit.com/r/Amd/comments/11btuar/powercolor_red_devil_7900_xtx_temperature_fixes/)
[^2]: [Powercolor Red Devil 7900 XTX - help with temps required](https://www.reddit.com/r/AMDHelp/comments/138fzje/powercolor_red_devil_7900_xtx_help_with_temps/)
[^3]: [PowerColor RX 7900XTX Red Devil with built-in manufacturing defect](https://www.igorslab.de/en/powercolor-rx-7900xtx-red-devil-mit-eingebautem-herstellungsfehler-wenn-der-hotspot-zum-standard-wird/)
