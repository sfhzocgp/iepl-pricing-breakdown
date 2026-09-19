# IEPL pricing: what a China–Hong Kong, Japan or US private line really costs — MKCloud's full plan and price list, shared vs dedicated bandwidth explained, and the coupons that actually stack

Searching for IEPL pricing usually ends the same way: you find either enterprise quotes that start at five figures, or forum posts yelling that everything cheap is fake. Both are half right. A true dedicated IEPL lease from a carrier runs roughly ¥150 per Mbps per month and up, with classic IPLC quotes often around ¥500/Mbps/month. Anything selling "IEPL" for the price of a coffee is almost always a shared slice of one — which isn't automatically bad, it just shouldn't be sold to you as a dedicated line.

That's where MKCloud (the site brands itself Mkcloud) is a useful reference point. It's a China-based cross-border line provider founded in 2023 that publishes its entire price list openly: traffic-billed plans from ¥158/month up to ¥18,428/month, and dedicated-bandwidth lines from ¥388/month into enterprise territory. Every plan is a KVM cloud server with the private line attached, dual independent IPv4 addresses (one for the entry, one for the exit), and monthly billing you can actually check before paying.

This article breaks down the full current price structure: every traffic-billed plan on each route, the dedicated-bandwidth entries, how billing and overage work, which coupon codes are floating around, and which tier makes sense for which workload.

## What you're actually paying for

Three product types sit under the "IEPL pricing" umbrella, and they cost very different amounts:

- **IEPL (International Ethernet Private Line)** — a point-to-point ethernet private line. On MKCloud's Guangzhou–Hong Kong route, the on-net latency is listed at 1–2 ms.
- **IPLC (International Private Leased Circuit)** — the classic leased-circuit product, used here for Shanghai→Japan (25–28 ms on-net), Shanghai→Hong Kong (21 ms) and Shanghai→US (124–134 ms) routes.
- **IXP / cloud-interconnect entry** — the line is the same on the exit side, but the China-side entry is a cloud-provider BGP network (Alibaba Cloud, Tencent Cloud, Baidu Cloud, Volcano, Huawei, UCloud, depending on route). You connect from a cloud server you already rent. This is why IXP plans run 20–40% cheaper than the direct-entry equivalents.

The economics are straightforward. When bandwidth is billed by Mbps on a truly dedicated basis, market rates for premium cross-border capacity start around ¥150/Mbps/month, and carrier IPLC can hit ¥500/Mbps/month. Traffic-billed plans flip the model: you get a shared peak bandwidth (say 150 Mbps or 1 Gbps) plus a monthly traffic quota, and pay a flat fee. MKCloud's entire traffic-billed range spans roughly ¥158–¥4,500/month, which is why this model dominates the budget end of IEPL pricing.

One honesty check before the tables: a shared "200 Mbps peak" is a peak, not a guarantee. A "5 Mbps dedicated" line, on the other hand, runs at 5 Mbps around the clock. Neither is better on its own — they price different resources.

## How MKCloud's plans are structured

Every plan on the store follows the same shape: a KVM VPS (1–28 cores, 2–64 GB RAM, 20–512 GB SSD) with the private line bound to it, two independent IPv4 addresses, and one of two billing modes:

- **Traffic-billed (shared bandwidth)** — fixed peak bandwidth, a monthly双向 (uplink + downlink combined) traffic quota, overage means suspension. Cheapest entry point: ¥158/month.
- **Bandwidth-billed (dedicated)** — the bandwidth is exclusively yours, traffic is unlimited, priced per Mbps. Cheapest entry point: ¥388/month for 5 Mbps on the Shanghai–HK route.

Two structural quirks matter for pricing. Direct-entry lines bind to **one Chinese province** (changeable later via ticket), and IXP lines require **a cloud BGP network as the front-end** — meaning you also rent an Alibaba/Tencent/etc. cloud server. That front-end cost is part of your real IEPL pricing math, and it's why the ¥158 tag on the Shenzhen–HK IXP plan isn't the whole story.

## Traffic-billed plans: the full price list

All prices below are monthly billing in CNY, as currently displayed on the official store pages. Config is CPU / RAM / SSD. Every plan includes dual independent IPv4.

### Guangzhou–HK IEPL (广港IEPL) — entry to Hong Kong, 1–2 ms on-net

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 500GB | 1C / 2GB / 20GB | 150 Mbps | 500 GB | ¥228 | [ View the 500GB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 1TB | 1C / 2GB / 20GB | 200 Mbps | 1 TB | ¥358 | [ View the 1TB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 2TB | 2C / 4GB / 40GB | 300 Mbps | 2 TB | ¥568 | [ View the 2TB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 4TB | 2C / 4GB / 40GB | 300 Mbps | 4 TB | ¥998 | [ View the 4TB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 6TB | 4C / 8GB / 60GB | 500 Mbps | 6 TB | ¥1,388 | [ View the 6TB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 10TB | 4C / 8GB / 60GB | 500 Mbps | 10 TB | ¥2,288 | [ View the 10TB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 20TB | 4C / 8GB / 60GB | 1 Gbps | 20 TB | ¥4,500 | [ View the 20TB plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |

Entry: Tencent Guangzhou BGP in, Hong Kong BGP out.

### Shanghai–Japan IPLC (沪日IPLC) — 25–28 ms on-net

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 1TB | 1C / 2GB / 20GB | 200 Mbps | 1 TB | ¥358 | [ Check Japan line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 2TB | 2C / 4GB / 40GB | 300 Mbps | 2 TB | ¥568 | [ Check Japan line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 4TB | 2C / 4GB / 40GB | 300 Mbps | 4 TB | ¥998 | [ Check Japan line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 6TB | 4C / 8GB / 60GB | 500 Mbps | 6 TB | ¥1,388 | [ Check Japan line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 10TB | 4C / 8GB / 60GB | 500 Mbps | 10 TB | ¥2,288 | [ Check Japan line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 20TB | 4C / 8GB / 60GB | 1 Gbps | 20 TB | ¥4,500 | [ Check Japan line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |

A 500 GB / 150 Mbps tier at ¥228/month has appeared on this route as a limited-time or new-customer package; whether it's live at any given moment is a store-page question, not a given.

### Shanghai–HK IPLC (沪港IPLC) — 21 ms on-net

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 1TB | 1C / 2GB / 20GB | 200 Mbps | 1 TB | ¥288 | [ See HK direct-line plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 2TB | 2C / 4GB / 40GB | 300 Mbps | 2 TB | ¥428 | [ See HK direct-line plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 4TB | 2C / 4GB / 40GB | 300 Mbps | 4 TB | ¥696 | [ See HK direct-line plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 6TB | 4C / 8GB / 60GB | 500 Mbps | 6 TB | ¥988 | [ See HK direct-line plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 10TB | 4C / 8GB / 60GB | 500 Mbps | 10 TB | ¥1,536 | [ See HK direct-line plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 20TB | 4C / 8GB / 60GB | 1 Gbps | 20 TB | ¥3,072 | [ See HK direct-line plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |

This is the line where longer billing cycles are officially documented: the entry plan runs ¥864 quarterly or ¥3,456 annually — flat 12× the monthly price, no hidden discount for prepaying.

### Shanghai–US IPLC (沪美IPLC) — 124–134 ms on-net

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 1TB | 1C / 2GB / 20GB | 200 Mbps | 1 TB | ¥428 | [ View US route plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 2TB | 2C / 4GB / 40GB | 300 Mbps | 2 TB | ¥698 | [ View US route plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 4TB | 2C / 4GB / 40GB | 300 Mbps | 4 TB | ¥1,258 | [ View US route plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 6TB | 4C / 8GB / 60GB | 500 Mbps | 6 TB | ¥1,758 | [ View US route plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 10TB | 4C / 8GB / 60GB | 500 Mbps | 10 TB | ¥2,888 | [ View US route plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 20TB | 4C / 8GB / 60GB | 1 Gbps | 20 TB | ¥5,666 | [ View US route plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |

Notice the tier ladder is identical across the Shanghai routes — same configs, different prices per direction. Latency and route cost drive the difference, not the hardware.

### Shenzhen–HK IXP (深港IXP) — cloud front-end required, 1–2 ms on-net

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 2TB | 2C / 4GB / 40GB | 1 Gbps | 2 TB | ¥158 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 4TB | 2C / 4GB / 40GB | 1 Gbps | 4 TB | ¥258 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 6TB | 4C / 8GB / 40GB | 2 Gbps | 6 TB | ¥378 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 10TB | 4C / 8GB / 40GB | 2 Gbps | 10 TB | ¥826 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 20TB | 4C / 8GB / 40GB | 2 Gbps | 20 TB | ¥1,639 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 30TB | 4C / 8GB / 60GB | 3 Gbps | 30 TB | ¥2,458 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 50TB | 8C / 8GB / 60GB | 3 Gbps | 50 TB | ¥3,588 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 100TB | 8C / 16GB / 80GB | 5 Gbps | 100 TB | ¥7,168 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 200TB | 8C / 16GB / 80GB | 5 Gbps | 200 TB | ¥12,288 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 300TB | 8C / 16GB / 80GB | 5 Gbps | 300 TB | ¥18,428 | [ Check IXP entry pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |

This is the cheapest entry in the whole catalog — 2 TB at a 1 Gbps peak for ¥158 — and the price gap vs the direct Guangzhou IEPL (¥568 for 2 TB at 300 Mbps) shows exactly what the cloud front-end requirement buys you in savings. One caveat from the store page itself: the Alibaba Cloud path into this line was listed as temporarily unavailable at the time of writing, so check the supported cloud list before ordering.

### Shanghai–Japan IXP (沪日IXP) — cloud front-end required, 25–28 ms

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 1TB | 2C / 4GB / 40GB | 200 Mbps | 1 TB | ¥166 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 2TB | 2C / 4GB / 40GB | 300 Mbps | 2 TB | ¥268 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 3TB | 2C / 4GB / 40GB | 500 Mbps | 3 TB | ¥358 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 6TB | 4C / 8GB / 40GB | 1 Gbps | 6 TB | ¥688 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 10TB | 4C / 8GB / 40GB | 1 Gbps | 10 TB | ¥1,125 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 20TB | 4C / 8GB / 40GB | 1 Gbps | 20 TB | ¥2,150 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 30TB | 4C / 8GB / 60GB | 2 Gbps | 30 TB | ¥3,165 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 50TB | 8C / 8GB / 60GB | 2 Gbps | 50 TB | ¥5,222 | [ View Japan IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |

### Shanghai–HK IXP (沪港IXP) — cloud front-end required, 21 ms

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 2TB | 2C / 4GB / 40GB | 500 Mbps | 2 TB | ¥198 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 3TB | 2C / 4GB / 40GB | 500 Mbps | 3 TB | ¥288 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 6TB | 4C / 8GB / 40GB | 1 Gbps | 6 TB | ¥398 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 10TB | 4C / 8GB / 40GB | 1 Gbps | 10 TB | ¥666 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 20TB | 4C / 8GB / 40GB | 1 Gbps | 20 TB | ¥1,290 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 30TB | 4C / 8GB / 60GB | 2 Gbps | 30 TB | ¥1,900 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 50TB | 8C / 8GB / 60GB | 2 Gbps | 50 TB | ¥3,120 | [ View HK IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |

### Shanghai–US IXP (沪美IXP) — cloud front-end required, 124–134 ms

| Plan | Config | Peak | Traffic | Price | Link |
| --- | --- | --- | --- | --- | --- |
| 1TB | 2C / 4GB / 40GB | 200 Mbps | 1 TB | ¥266 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 2TB | 2C / 4GB / 40GB | 200 Mbps | 2 TB | ¥430 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 3TB | 2C / 4GB / 40GB | 500 Mbps | 3 TB | ¥615 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 6TB | 4C / 8GB / 40GB | 500 Mbps | 6 TB | ¥1,166 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 10TB | 4C / 8GB / 40GB | 1 Gbps | 10 TB | ¥1,945 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 20TB | 4C / 8GB / 40GB | 1 Gbps | 20 TB | ¥3,686 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 30TB | 4C / 8GB / 60GB | 2 Gbps | 30 TB | ¥5,529 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 50TB | 8C / 8GB / 60GB | 2 Gbps | 50 TB | ¥9,216 | [ View US IXP plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |

## Dedicated-bandwidth plans: the other half of IEPL pricing

If your workload is continuous transfer — backups, video, sustained syncing — a shared peak won't cut it. MKCloud's bandwidth-billed lines trade the traffic quota for a guaranteed rate, and the pricing steps up accordingly:

| Line | Entry tier | Entry price | Notes | Link |
| --- | --- | --- | --- | --- |
| Shanghai–HK IPLC dedicated (沪港IPLC独享) | 5 Mbps, unlimited traffic, 2C/4GB/40GB | ¥388/mo | Higher tiers up to 100 Mbps on the store page | [ View dedicated HK entry plan](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| Shanghai–HK IXP dedicated (沪港IX独享) | 100 Mbps | ¥2,500/mo | 200M ¥4,600 / 500M ¥11,000 / 1G ¥19,000 / 2G ¥38,000 / 5G ¥95,000; custom configs via inquiry | [ View IXP dedicated plans](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-ex) |
| Shenzhen–HK IXP dedicated (深港IX独享) | 100 Mbps | ¥1,600/mo | 200M ¥3,000 / 500M ¥6,000 / 1G ¥9,000 / 2G ¥16,000 / 5G ¥35,000 | [ Check Shenzhen dedicated pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |
| Shanghai–Japan dedicated (沪日独享) | 100 Mbps | from ¥2,100/mo | 2–28 cores, 4–32GB, 100–5,000 Mbps configurable | [ View Japan dedicated options](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| Xiamen–HK high-defense IPLC dedicated (厦港高防IPLC独享) | 200 Mbps | ¥6,000/mo | Includes DDoS protection, 1–2 ms on-net | [ Check high-defense line pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fxm-hk-ex) |
| Guangdong triple-line / carrier IEPL dedicated (广东三线/单线IEPL独享) | 200 Mbps | quoted on store page | 200M–2,000M range across telecom/unicom/mobile/triple-line entries, with 300 Gbps DDoS protection; volume pricing negotiable | [ View Guangdong IEPL dedicated lines](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| Guangzhou–HK IEPL dedicated (广港IEPL独享) | 5–100 Mbps range | quoted on store page | Direct-entry dedicated with unlimited traffic | [ Check dedicated IEPL pricing](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| Other dedicated routes (Shanghai BGP-entry HK/JP/US, Shanghai–US dedicated, Shanghai CN2, Fujian anti-DDoS) | various | quoted on store page | Same VPS + line structure; live prices on each product page | [ Browse the full store catalog](https://bit.ly/MKCLoud) |

A sanity check on that ¥388 entry: 5 Mbps dedicated and 200 Mbps shared peak cost similar money because they bill different things. If your traffic arrives in bursts — store admin work, image uploads, API calls — the shared peak is almost always the better deal. If something runs hot 24/7, per-Mbps dedicated pricing is the honest comparison against carrier quotes of ¥150+/Mbps/month, and MKCloud's dedicated entries land well under that benchmark.

## Coupons, and what they're actually worth

Codes come and go with campaign periods, so treat this as "confirmed to exist, verify at checkout":

| Code | Applies to | Discount | Example |
| --- | --- | --- | --- |
| `MK-8.8` | Traffic-billed plans | 12% off, recurring | ¥228 → ~¥201/mo |
| `MK-7.8` | Dedicated-bandwidth plans | 22% off first month | — |
| `MK-IEPL-WELCOME` | IEPL products | 10% off | ¥228 → ~¥205/mo |
| `MK-IPLC-WELCOME` | IPLC products | 10% off | — |
| `IXCLOUD` | IXP cloud-interconnect plans | 31% off | ¥268 → ¥184.92/mo |
| `US-6.9` | US-direction IXP plans | 31% off | — |
| `CLOUD-2T-NEW` | 2TB cloud-interconnect plan | 20% off | ¥158 → ¥126/mo |
| `ALIYUN` | Cloud-whitelist HK pioneer plan | 12% off | ¥98 → ¥86/mo |
| `MK-NEW` | New-customer bundle | fixed bundle price | 2C4G / 268 Mbps / 666 GB at ¥236/mo |

Two practical notes. The 8.8/7.8 pair has appeared in multiple campaign cycles through 2025–2026 and is described as recurring (it applies on renewal too), but MKCloud's own knowledge base marks these codes as valid "during the activity period" — so the checkout page, not this article, is the final word. And discount codes don't stack; one code per order.

Also worth knowing: if you blow through a traffic quota mid-month, there's a self-service traffic reset priced at 90% of the plan price, and upgrades/downgrades go through a ticket (downgrade differences aren't refunded).

## Which tier matches which workload

**Solo seller running one or two store backends against Hong Kong.** Guangzhou–HK IEPL 500GB at ¥228 does the job — 1–2 ms on-net latency makes admin panels feel local, and 500 GB of combined traffic covers a month of dashboard work and product uploads. With `MK-8.8` you're near ¥200, roughly $28.

**Multi-account operations that need clean, isolated IPs.** The dual independent IPv4 (entry + exit) is the point here — every plan gets its own pair, and third-party reviewers checking the IP ranges against scamalytics-style databases reported no blocklist flags. Step up to 1TB–2TB tiers once you're pushing media uploads.

**Japan-facing workloads on a budget.** The Shanghai–Japan IXP 2TB at ¥268 (or ¥184.92 with `IXCLOUD`) is the value pick — but only if you already rent an eligible cloud server, because the entry requires it. If you don't want a front-end machine, the direct 沪日IPLC 1TB at ¥358 is simpler.

**US-heavy workloads.** Latency is what it is at 124–134 ms — this route exists for reaching US platforms, not for snappiness. 沪美IPLC 1TB at ¥428 with a Shanghai Telecom entry, or 沪美IXP 1TB at ¥266 if you're cloud-based.

**Serious sustained bandwidth.** This is where the dedicated table matters: ¥1,600/month buys 100 Mbps guaranteed on the Shenzhen–HK IXP route, which undercuts per-Mbps carrier pricing by a wide margin. Above 1 Gbps you're in negotiated-price territory.

## Before you click buy

The store's own checkout notice spells out the constraints, and they're real pricing factors:

> All products are cloud/dedicated servers, not proxy services. Real-name registration with Chinese identity information is required. Direct-entry lines bind to one province; IXP lines require a supported cloud BGP network as the front-end. Refunds are only accepted for verified quality issues (with latency/speed evidence via ticket), and no region switching after activation.

Payment is Alipay only. The terms explicitly prohibit proxy-pool ("airport") and return-to-China usage, with termination without refund as the penalty — if that's your use case, this isn't your product, and no amount of coupon math changes it.

On reliability: independent discussion threads on NodeSeek describe the lines as steady in daily use, with the recurring theme that the experience "leans heavily on your front-end" — meaning IXP users live or die by the quality of their cloud server and local connection. MKCloud also isn't a hyperscaler, and at least one independent review makes the reasonable suggestion to start with monthly billing rather than annual prepay if provider longevity is a concern. Monthly is the default anyway; longer cycles exist but, on the Shanghai–HK line at least, they don't discount.

## Quick answers

**How much does IEPL cost per month, realistically?** For a China–HK route with shared peak bandwidth and a traffic quota: ¥158–¥228 gets you started at MKCloud, and comparable traffic-billed offerings cluster in that range. True dedicated IEPL starts around ¥388/month for 5 Mbps and climbs linearly with bandwidth; carrier-grade IPLC by the Mbps runs ¥500/Mbps/month or more.

**Is a cheap "IEPL" plan really IEPL?** The underlying transport can genuinely be IEPL/IPLC while being sold as shared capacity on a VPS. That's the standard model at this price point — MKCloud includes it in the product name itself ("traffic-billed shared bandwidth"). What you should refuse to pay for is a dedicated price for a shared line.

**Does annual billing save money?** On the documented Shanghai–HK entry plan, no: ¥864 quarterly and ¥3,456 yearly are exact multiples of ¥288. Discount codes are where the savings are.

**What happens when traffic runs out?** Suspension on current store pages. Fixes: a self-service reset at 90% of the plan price, or a ticket-based upgrade.

The short version of IEPL pricing at MKCloud: ¥158–¥228/month puts a real private line with independent dual IPs under a small e-commerce operation; ¥400–¥1,400/month covers multi-account and heavier traffic across Japan and US routes; and the moment "continuous" enters your requirements, the dedicated table — not the shared one — is where you should be comparing.
