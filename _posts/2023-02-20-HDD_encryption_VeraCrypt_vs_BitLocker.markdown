---
layout: post
title:  "HDD Encryption: VeraCrypt vs BitLocker"
date:   2023-02-20 23:30:00 +0200
categories: VeraCrypt HDD 
---
Recently I bought new HDD to expand storage capabilities in my PC. This seemed
like a good time to evaluate if my software of choice for encrypting HDDs
(VeraCrypt) is still the best choice available, especially for large HDDs, in
this case 12TB HDD.

<!--more-->

My search for full disk encryption software for Windows showed, that choice is
suprisingly small. A lot of tools are not maintained anymore (DiskCryptor),
closed source (BestCrypt) or just not tested enough for me to trust it. In the
end, the most suitable candidate seemed to be VeraCrypt[^1], which I was already
using for smaller, older drives.

Despite not finding any alternatives to VeraCrypt, I still wanted to test if
VeraCrypt will have any impact on performance of my new HDD and compare it with
some other encryption tool. Windows 10 Pro has integrated BitLocker, which
seemed like a natural candidate for comparison.

Test setup:
* Ryzen 9 3900X
* ASRock X570 Taichi
* GSkill F4-3200C14D-32GTZKW (2x16GB B-Die)
* Samsung 980Pro 1TB (system)
* Palit Gamerock Premium GTX1080
* **Toshiba X300 12TB (HDWR21C)**

Drive had GPT partition table. I tested only first partition, which was 9.5TB
in size. HDD is 4Kn/512e drive.

Used software versions:

| Software | Version |
|:--------:|:-------:|
| VeraCrypt | 1.25.9 |
| Crystal Disk Mark | 8.0.4 x64 |
| ATTO Disk Benchmark | 4.00.0f2 |

## CrystalDiskMark

CrystalDiskMark (CDM) runs were done with number of tests set to 5 and test
file size to 4GB.

# Sequential 1M

![Crystal Disk Mark Sequential](/assets/VeraCrypt_vs_BitLocker/cdm_seq.png)
{: style="text-align:center"}

Encryption does not have any impact on results of sequential 1M tests in
CDM. Results are within margin of error.

# Random 4K

![Crystal Disk Mark Random 4K](/assets/VeraCrypt_vs_BitLocker/cdm_random.png)
{: style="text-align:center"}

VeraCrypt shows a significant drop in the read test with (but not write!) with
high queue depth, but that is the only scenario where any meaningful
differences were observed in this benchmark.

## ATTO Disk Benchmark

ATTO runs were done with following settings:

| I/O Size | 512 B to 64 MB |
| File Size | 256 MB |
| Direct I/O | Enabled |
| Bypass Write Cache | Disabled |
| Verify Data | Disabled |

# QD1

![ATTO QD1](/assets/VeraCrypt_vs_BitLocker/atto_qd1.png)
{: style="text-align:center"}

With queue depth of 1 in ATTO, we already see some differences between
encryption methods, which was not really the case with CDM. VeraCrypt writes
are visibly slower for I/O sizes below 64 KB. For bigger I/O sizes results
for drive encrypted with VeraCrypt are almost the same as transfers speeds
for unencrypted drive. With BitLocker we can see small drop in performance
with I/Os bigger than 16 KB.

# QD4

![ATTO QD4](/assets/VeraCrypt_vs_BitLocker/atto_qd4.png)
{: style="text-align:center"}

With QD=4 the gap in performance caused by VeraCrypt, for I/O sizes below
32 KB, is even bigger than in case of QD=1. Both read and write speeds are
affected. The biggest suirprise for me is the performance of BitLocker
encrypted drive when it comes to writing with I/Os above 2 MB. The performance
drops from around 220 MB/s to 150 MB/s.

## Conclusions

Both benchmark react differently to encryption. CMD does not show any
performance drop caused by encryption with either method, other than
pretty big drop in transfer speeds of reading random 4k blocks with
high queue depth when volume is encrypted with VeraCrypt. ATTO on the
other hand shows much bigger differences between encrypted and unencrypted
drive.

I am not really familiar enough with HDD benchmarks to explain why those
differences between benchmarks are observed. From what I gathered CDM uses
incompressible data, while ATTO uses compressible data. Tests were also
executed with different test file size (at least if I understand options
of each tool correctly! :-)). There are also big differences in how the
benchmarks are implemented (if someone wants to check CDM is open source[^2]).

Summing up, it is clear that encrypting HDD with VeraCrypt will have a negative
impact on performance when it comes to reading and writing with small I/O sizes.
The impact will be bigger with bigger queue depth. In my use case is completely
acceptable (I am not keeping OS on the encrypted drive). VeraCrypt is probably
still most reputable full disk encryption software for Windows and despite its
development team being small (from what I understand it is just 1 person) it is
still being developed and maintained.

[^1]: [VeraCrypt homepage](https://www.veracrypt.fr/)
[^2]: [CrystalDiskMark on GitHub](https://github.com/hiyohiyo/CrystalDiskMark)
