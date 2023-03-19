---
layout: post
title:  "HDD Evolution - Benchmarks!"
date:   2023-03-19 15:00:00 +0200
categories: HDD 
---
I went through my stash of hard drives, which I accumulated over past ~15 years
to check which of them are still working, while doing so I run some benchmarks
to compare their performance and see how HDDs evolved in the past decade. Here
are the results!

<!--more-->

## Test setup

* Ryzen 9 3900X
* ASRock X570 Taichi
* GSkill F4-3200C14D-32GTZKW (2x16GB B-Die)
* Samsung 980Pro 1TB (system)
* Palit Gamerock Premium GTX1080

## HDDs in test

| Model | Capacity | Form factor | RPM | Manufactured |
|:--------:|:-------:|:-------:|:--------:|:-------:|:-------:|
| Samsung SP2504C | 250GB | 3.5" | 7200 | 02/2006 |
| Samsung HD103SJ | 1TB | 3.5" | 7200 | 09/2009 |
| WD Scorpio Blue WD3200BEVT | 320GB | 2.5" | 5400 | 11/2010 |
| WD Blue WD10EZEX | 1TB | 3.5" | 7200 | 10/2014 |
| Seagate ST4000DM000 | 4TB | 3.5" | 5900 | 12/2015 |
| Seagate Barracude ST4000DM005	| 4TB | 3.5" | 5900 | 04/2017 |
| Toshiba X300 HDWR21C | 12TB | 3.5" | 7200 | 08/2021 |

## CrystalDiskMark

# Sequential 1M

![Crystal Disk Mark Sequential](/assets/HDD_evolution/cdm_seq1m.png)
{: style="text-align:center"}

The fastest drive (HDWR21C) is more than 3 times faster than the slowest one (SP2504C)!

# Random 4K

![Crystal Disk Mark Random 4K](/assets/HDD_evolution/cdm_rnd4k.png)
{: style="text-align:center"}

With 4k transfers we can also see some improvements over the years, although
not as big as with sequential read/write. Not to mention that any SSD will
actually "demolish" those results.

## HD Tune read plots

Below results of HD Tune read test for different drives.

# Samsung SP2504C

![Samsung SP2504C HDTune plot](/assets/HDD_evolution/hd_tune_SAMSUNG_SP2504C_read.png)
{: style="text-align:center"}

# Samsung HD103SJ

![Samsung HD103SJ HDTune plot](/assets/HDD_evolution/hd_tune_SAMSUNG_HD103SJ_read.png)
{: style="text-align:center"}

# WD Scorpio Blue WD3200BEVT

![WD Scorpio Blue WD3200BEVT HDTune plot](/assets/HDD_evolution/hd_tune_WDC_WD3200BEVT_read.png)
{: style="text-align:center"}

# WD Blue WD10EZEX

![WD Blue WD10EZEX HDTune plot](/assets/HDD_evolution/hd_tune_WDC_WD10EZEX_read.png)
{: style="text-align:center"}

# Seagate ST4000DM000

![Seagate ST4000DM000 HDTune plot](/assets/HDD_evolution/hd_tune_SEAGATE_ST4000DM000_read.png)
{: style="text-align:center"}

# Seagate Barracude ST4000DM005

![Seagate Barracude ST4000DM005 HDTune plot](/assets/HDD_evolution/hd_tune_SEAGATE_ST4000DM005_read.png)
{: style="text-align:center"}

# Toshiba X300 HDWR21C

![Toshiba X300 HDWR21C HDTune plot](/assets/HDD_evolution/hd_tune_TOSHIBA_HDWR21C_read.png)
{: style="text-align:center"}
