---
layout: post
title:  "PowerColor 7900XTX Red Devil: Final solution"
date:   2025-07-06 13:30:00 +0200
categories: GPU PowerColor 7900XTX 
---
I am pretty sure I have fixed the thermal issues with my 7900XTX!
<!--more-->

# Background

I described the issues I had with the temperatures on my PowerColor 7900XTX
on this page twice already:
[here]({% post_url 2023-07-10-PowerColor_7900XTX_Red_Devil_issue_with_TIM %}) and
[here]({% post_url 2024-07-07-PowerColor_7900XTX_Red_Devil_Further_down_the_Spiral %})
(seems like I post about this card every year or so, but hey I never promised
regular updates here!).

Anyway, since getting this card hotspot temperature was always an issue.
Repasting, even with high viscosity paste, solved the issue for 2-3 months,
but afterwards problem was back. With fresh paste temperature delta between
core and hotspot temp was always in the 20s, later the delta rose to 30-35
degrees. Additionally, after tearing the original memory thermal pads during
repasting, I was not able to find a good replacement for them, my memory
junction temps were worse than stock ones. I was bit annoyed with that
situation, luckily, the Internet helped me again!

# Solution

While browsing the web for the solution I run into gentleman called Snark,
his YouTube channel [^1] and Discord [^2] server. After lurking ithere for
a bit, the conclusion was clear - try the famous Honeywell PTM7950 on the
GPU core and thermal putty on the RAM and VRMs. I had both PTM7950 and some
Upsiren UTP-8 at my place already, so I went with it!

![Red Devil 7900XTX PTM + thermal putty applied](/assets/PowerColor_7900XTX_TIM3/tim_putty_repaste.jpg)
{: style="text-align:center"}

It was me first time applying putty, so application is not perfect, also I run
out of UTP-8 and I had to put Thermal Grizzly putty on one set of VRMs. However
it has been 8 months since I applied PTM - my core to hotspot delta stays under
30 K, memory junction temp is also as good as before disassembling the card
(stays under 90 °C).

Seems that PTM7950 is really worth the hype it is causing in the community.
It is definitely good for counteracting the famous "pump out" effect and it
is supposed to have a really long lifespan. I would really recommend it for
big dies like the one on the 7900XTX. I am also really happy to see it being
used on new GPUs by some manufacturers (e.g Sapphire RX 9000 cards).

Thermal putty also seems like a good idea if one is not sure which thermal pad
to use. There is so many pads on the market, with various hardness and thickness,
that finding our the right pads to use can be difficult.

[^1]: [Snarks Domain YouTube channel](https://www.youtube.com/@snarksdomain)
[^2]: [Snarks Domain Discord](https://discord.com/invite/C44b5UNCNm)
