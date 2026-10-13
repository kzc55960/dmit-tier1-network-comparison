# DMIT Tier 1: What $36.90 a Year Actually Buys You, Who Should Skip CN2 GIA, and How to Pick Between LAX, HKG, and TYO

Most people typing "DMIT Tier 1" into a search box are stuck on the same question: the hardware looks identical to DMIT's CN2 GIA plans, so why is the Tier 1 line a third of the price? Is it the same product with a cheaper sticker, or is something being quietly taken away?

Something is being taken away, but not the part you might assume. It isn't CPU, memory, or disk. It's the routing to mainland China — and whether that matters depends entirely on where your users actually are.

Here's what the line is, what the plans cost, and where the tradeoff stops being worth it.

## Three network series, one hardware platform

DMIT splits its Los Angeles, Hong Kong, and Tokyo inventory into three network profiles, and the naming is consistent across all three locations:

- **Premium** — sold as `Pro`. The profile includes Tier 1 transit plus premium providers, including China Telecom's CN2 GIA. Most expensive, lowest latency into mainland China.
- **Eyeball** — sold as `EB`. A middle tier that makes a "reasonable effort" at China routing via CMI or similar carriers. Cheaper than Pro, aimed mostly at mobile users.
- **Tier 1** — sold as `T1`. International routing only. DMIT's own product copy describes it as optimizing latency for Europe–Asia and intra-Asia traffic, explicitly *without* China optimization.

The hardware underneath doesn't change between them. On the Tokyo node, DMIT states the facility runs exclusively on AMD EPYC 7003 series CPUs with all-NVMe storage, and the same EPYC 7003 platform (what DMIT labels AS3) underpins the Tier 1 plans in Los Angeles and Hong Kong.

So when you buy Tier 1, you're not buying a worse server. You're buying the same box with a cheaper transit mix wired into it. That's the entire premise of the line, and every other difference follows from it.

## The tradeoff people underestimate

Tier 1 traffic leaves and enters through general international carriers. Third-party writeups of the Hong Kong Tier 1 line report it riding RETN, which is genuinely good for Hong Kong-to-Europe paths. The Tokyo Tier 1 line is commonly reported to run NTT in both directions with occasional US detours via Lumen, with mobile traffic often exiting through CMI.

None of that is optimized for someone in Shanghai or Guangzhou pulling a page.

The practical consequence is counterintuitive and worth repeating: a Tier 1 node in Hong Kong can deliver *worse* latency to mainland China than a Premium node in Los Angeles. People buy Hong Kong Tier 1 assuming proximity equals speed, then wonder why the connection crawls. Proximity is not the variable that matters here. The transit path is.

👉 [Check DMIT's live Tier 1 stock and pricing](https://www.dmit.io/aff.php?aff=12046)

## Where Tier 1 genuinely wins

Three things, and they're not small.

**Port speed.** Entry plans ship with a 4Gbps port; from STARTER upward you're on 10Gbps. That's a lot of headroom for the money, and it's the same port speed the premium lines get.

**Traffic, billed one direction.** Tier 1 counts traffic as the larger of inbound or outbound, not the sum. Most providers bill both directions combined, which effectively halves your usable allowance. A 2TB Tier 1 allowance goes further than 2TB elsewhere.

**Overage throttles instead of suspending.** This is the difference that decides a lot of purchases. On the Premium and Eyeball lines, exceeding your monthly allowance drops you to single-digit Mbps or pauses the service entirely — the published tables for those plans show figures in the 4–10Mbps range. Tier 1 keeps you running: the WEE plan in Los Angeles holds 100Mbps, WEE in Hong Kong and Tokyo holds 50Mbps, mid-tier plans run 100–200Mbps, and the largest plans keep 500Mbps to 1Gbps.

If your workload is bursty — backups, mirrors, image pipelines, bulk transfers between regions, a CDN origin serving a global audience — that overage behavior is worth more than a nicer route you'll never use.

## The full Tier 1 lineup

Stock on this line moves constantly, and DMIT rotates which plans are orderable. Confirm on the order page before you plan around anything below. Prices are USD.

| Location | Plan | vCPU | RAM | SSD | Traffic / Port | After overage | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Los Angeles | LAX.AS3.T1.WEE | 1 | 1GB | 20GB | 1000GB @ 4Gbps | 100Mbps | $36.90/year | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Los Angeles | LAX.AS3.T1.TINY | 1 | 1GB | 20GB | 2000GB @ 4Gbps | 200Mbps | $6.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Los Angeles | LAX.AS3.T1.STARTER | 2 | 2GB | 40GB | 4000GB @ 10Gbps | 200Mbps | $12.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Los Angeles | LAX.AS3.T1.MINI | 2 | 4GB | 80GB | 8000GB @ 10Gbps | 200Mbps | $21.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Los Angeles | LAX.AS3.T1.MICRO | 4 | 4GB | 120GB | 16000GB @ 10Gbps | 500Mbps | $32.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.WEE | 1 | 1GB | 20GB | 1000GB @ 4Gbps | 50Mbps | $36.90/year | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.TINY | 1 | 1GB | 20GB | 2000GB @ 4Gbps | 100Mbps | $6.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.STARTER | 1 | 2GB | 40GB | 4000GB @ 10Gbps | 100Mbps | $12.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.MINI | 2 | 2GB | 60GB | 8000GB @ 10Gbps | 100Mbps | $21.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.MICRO | 4 | 4GB | 80GB | 16000GB @ 10Gbps | 200Mbps | $32.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.MEDIUM | 4 | 8GB | 160GB | 32000GB @ 10Gbps | 200Mbps | $49.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.LARGE | 8 | 16GB | 320GB | 64000GB @ 10Gbps | 500Mbps | $99.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Hong Kong | HKG.AS3.T1.GIANT | 8 | 24GB | 640GB | 128000GB @ 10Gbps | 1Gbps | $199.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.WEE | 1 | 1GB | 20GB | 1000GB @ 4Gbps | 50Mbps | $36.90/year | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.TINY | 1 | 1GB | 20GB | 2000GB @ 4Gbps | 100Mbps | $6.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.STARTER | 1 | 2GB | 40GB | 4000GB @ 10Gbps | 100Mbps | $12.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.MINI | 2 | 2GB | 60GB | 8000GB @ 10Gbps | 100Mbps | $21.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.MICRO | 4 | 4GB | 80GB | 16000GB @ 10Gbps | 200Mbps | $32.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.MEDIUM | 4 | 8GB | 160GB | 32000GB @ 10Gbps | 200Mbps | $49.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.LARGE | 8 | 16GB | 320GB | 64000GB @ 10Gbps | 500Mbps | $99.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |
| Tokyo | TYO.AS3.T1.GIANT | 8 | 24GB | 640GB | 128000GB @ 10Gbps | 1Gbps | $199.90/month | [View plan](https://www.dmit.io/aff.php?aff=12046) |

A note on that table: third-party listings of this line disagree with each other on RAM and disk sizes for a few Hong Kong and Tokyo tiers — the TINY plan shows up as either 1GB/20GB or 0.75GB/10GB depending on which page you read. Treat the order page as the only figure that counts. WEE appears as an annual-only plan in every listing I checked.

One more caveat that comes from DMIT rather than a reseller: the company has flagged the Los Angeles AS3 platform as still being in an optimization phase, meaning disk performance and SLA may sit below its more mature platforms. If you're deploying something that matters, test before you commit.

## LAX vs HKG vs TYO: pick by audience, not by map

**Los Angeles** — the cheapest way in, and the shortest plan ladder (five tiers as listed). WEE at $36.90/year for 1 vCore, 1GB, and a 1TB allowance with a 4Gbps port is the lowest entry price in the whole Tier 1 line. Best fit for US and global audiences, or as a relay node for trans-Pacific traffic.

**Hong Kong** — the same prices as Tokyo and LA, but a longer ladder up to GIANT. The reported RETN routing gives it an edge on Asia–Europe paths. If the people hitting your service are in Europe or Southeast Asia, this is the node to look at.

**Tokyo** — housed at Equinix TY8 in Shinagawa, with DMIT quoting up to 1.4Tbps of Tier 1 transit capacity and direct interconnects with major Japanese ISPs. For Asia-Pacific coverage — Japan, Korea, Taiwan, Southeast Asia — and for data moving between regions, it's the most capable of the three on paper.

The mistake to avoid is buying the node closest to you if your traffic comes from somewhere else. Match the node to the audience.

## What it actually costs per month

The WEE plan is the number everyone anchors on: $36.90 a year works out to about $3.08 a month for 1 vCore, 1GB RAM, 20GB SSD, and a 1TB monthly allowance on a 4Gbps port. Nothing else in the DMIT catalog comes close on entry price.

The first meaningful step up is STARTER at $12.90/month, which is where you get 2 vCores, 4TB of traffic, and the 10Gbps port. Everything between WEE and STARTER is a traffic increase rather than a real configuration jump — if you're weighing TINY at $6.90/month against WEE, the honest question is whether you need monthly billing flexibility, because TINY at $6.90 monthly roughly doubles what WEE costs annually.

On discounts: DMIT doesn't publish public Tier 1 coupon codes on its own site, and the third-party coupon pages that circulate (recurring 30% off on Hong Kong and Tokyo Tier 1 for quarterly billing and longer, 10% off on Los Angeles Tier 1, both excluding WEE) are updated inconsistently and I can't confirm any of them are still active. The checkout has a **Validate Code** field — enter a code there and see whether it sticks before you pay. If it doesn't validate, annual billing on WEE is already the discount.

There's also a running caveat worth knowing about: several of the entry plans, including WEE and TINY, are frequently described in third-party listings as permanently excluded from coupons. Don't count on a code to sweeten the cheapest plans.

👉 [Compare the currently orderable Tier 1 plans](https://www.dmit.io/aff.php?aff=12046)

## Details that decide the purchase

Every Tier 1 plan ships with one IPv4 and one IPv6 /64 block, KVM virtualization, and DDoS protection as standard. Traffic accounting is one-directional — the larger of in or out. Payment options include Alipay, PayPal, credit card, and WeChat Pay, which matters if you're not in a card-friendly region.

Before you buy, use the test infrastructure rather than trusting a review. Reported test IPs include 154.12.176.28 for Hong Kong Tier 1 and 154.31.112.5 for Tokyo Tier 1, and DMIT runs a looking glass at `lg.dmit.sh` with per-node profiles (`?server=tyo-t1` and similar). Ping it from where your users actually are, at the hour they actually use the service. Route quality on international paths changes noticeably at peak.

## Who should buy Tier 1

Buy it if your audience is outside mainland China, if you're building a relay or landing node, if your workload is bandwidth-heavy and bursty, or if you want a cheap independent machine that stays reachable after burning through its allowance. A 1 vCore, 1GB box on a 4Gbps port for $36.90 a year is a good deal on those terms.

Skip it if your users are in mainland China and latency matters to them. That's what Premium is for, and the price gap is the cost of the routing — not a markup on the hardware. Paying for Tier 1 and expecting GIA behavior is the one way to be genuinely disappointed by this line.

👉 [See what's in stock on DMIT's Tier 1 line right now](https://www.dmit.io/aff.php?aff=12046)
