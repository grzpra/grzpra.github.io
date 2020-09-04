---
layout: post
title:  "Strange issue with my 3900X"
date:   2020-09-04 13:00:00 +0200
categories: 3900X CPU 
---
Few days ago I found out that my 24/7 system with Ryzen 9 3900X fails prime95
torture test when calculating FFTs with a length of 16K or 20K with AVX2
enabled.

<!--more-->

This seemed a bit strange to me, because I actually never overclocked this
CPU and the problem occurs both on total BIOS defaults as well as when infinity
fabric clock and memory clock are set to 1866/3733. Other than this very
specific case, system seems to be 100% stable. It passes OCCT Small data set
AVX2 test for over 9 hours, it passes prime95 AVX2 with all other FFT lengths
in the 1-64K range for hours, but 16K and 20K fails within few minutes. The
fails only occur on worker threads 17,18,21 and 22, as far as I know prime95
always assigns same workers to same CPUs, which would suggest that only 2 out
of 12 cores are failing. I run prime95 with SUM(INPUTS) error and Rounding
checking enabled. I read about other people having similar problems
with their Ryzen 3000 series CPUs[^1], but those reports were mostly about
3950X.

I am not sure if this issue actually occurred with my CPU from the first day or
is it something which started only recently. As mentioned before I only
observed this behavior few days ago, as I do not run prime95 with smallFFT
preset (which includes 16K and 20K) that often. I definitely run it just after
I got my new setup working (summer last year), but back then all BIOSes
available for my motherboard had awfully broken PPT/TDC/EDC reporting and that
made CPU boost behave in very funky way, because of that I cannot really
compare situation back then with present.

My setup consists of:
* Ryzen 9 3900X
* ASRock X570 Taichi
* GSkill F4-3200C14D-32GTZKW (2x16GB B-Die)
* Samsung EVO 850 500GB
* Palit Gamerock Premium GTX1080
* Noctua NH-D15S
* Corsair AX860

So far I tried following things to fix this:
* clearing CMOS - does not help;
* latest AMD chipset drivers (2.07.14.327) - nothing changes;
* different BIOSes for my motherboard - 3.00; 3.20 and 3.40 - all behave
the same way;
* running with just 1 stick of RAM - issue still occurs;
* enabling PBO - seems to help a bit (the error occurs bit later), this is
most likely due to higher VCore being applied to the CPU, but I cannot make it
pass the 16K test with PBO alone (maybe I need to test more combinations
of PBO params);
* enabling Vcore offset of +50mV - this seems to fix the issue, but it makes
the CPU runs slightly slower (higher Vcore, higher power usage - boost
algorithm slows down the CPU faster);
* disabling AVX2 in prime95 - it is not really a fix, but the issue was not
observed with AVX2 disabled.

I tried contacting both motherboard manufacturer (ASRock) and AMD, but I did
not get any significant tips. However AMD support acknowledged that it MIGHT
BE CPU defect. Both parties suggested trying CPU in different rig, but I can't
do it at the moment.

In my opinion it seems that CPU just can't cope with prime95 16K FFT AVX2
test, because the voltage/frequency curve on which it operates is just too
aggressive. On default settings it should be able to pass everything prime95 is
throwing at it. The whole issue is not a big thing, but it is kind of annoying
knowing that not so cheap CPU is not fully stable at default settings. My CPU
is from early batches as I got it in summer 2019 and from what I heard the
silicon quality got better over time, so hopefully new CPUs are totally stable
even under prime95 and I am just unlucky with my chip.

I am still investigating this issue and I will update this post when/if I find
some solution.

[![prime95 16k fail screenshot](/assets/Ryzen3900x_prime95_issue/ryzen3900x_prime95_16_def_fail_thumb.jpg)](/assets/Ryzen3900x_prime95_issue/ryzen3900x_prime95_16_def_fail.png)
{: style="text-align:center"}

[^1]: [Stock 3950x crashes with prime95 small FFTs@overclock.net](https://www.overclock.net/forum/10-amd-cpus/1744592-stock-3950x-crashes-prime95-small-ffts.html)

