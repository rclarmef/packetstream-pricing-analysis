# packetstream pricing: what the $1/GB rate really costs, the $50 minimum, and when a per-IP plan beats it

PacketStream's pricing is one of the shortest pricing pages in the proxy industry, which is either refreshing or frustrating depending on what you came for. There's no Basic/Pro/Enterprise ladder to decode. Just a rate, a minimum, and a note that the balance doesn't expire.

Here it is, before any of the caveats: **$1.00 per GB, metered at the gateway, with a $50 minimum purchase and no subscription.** That's what PacketStream publishes on its own site and repeats in its FAQ. Wholesale buyers get the same $1.00/GB headline rate with a $500 minimum commitment, per the same FAQ.

The rest of this article is about what those three numbers actually mean once you plug in real workloads — because "$1/GB" tells you almost nothing until you know how much bandwidth your scraper burns and how long you're willing to wait for a useful session. And because there's a second pricing shape in this market — paying per IP instead of per GB — that costs less for a specific and fairly common type of job.

## PacketStream's published prices, line by line

| What you're buying | Published price | Minimum / validity |
| --- | --- | --- |
| Residential proxy bandwidth (retail) | $1.00 / GB, metered at the gateway | $50 minimum purchase, no subscription, balance does not expire |
| Residential proxy bandwidth (wholesale) | From $1.00 / GB | $500 minimum purchase |
| Packeter earnings (selling your bandwidth) | $0.10 per GB of customer traffic routed through your connection | Cashout once balance hits $5, 3% cashout fee, PayPal payouts processed within a week |

A few things worth pulling out of that table.

There are no volume tiers. An independent 2026 pricing index that scraped provider pricing pages lists PacketStream's pay-as-you-go rate and its cheapest-tier rate as the same number — $1.00. Compare that to most residential networks, where the per-GB price collapses as your monthly commit grows and the advertised entry price is a tier almost nobody qualifies for.

The $50 minimum is a top-up threshold, not a subscription. You fund the account once and burn the credit at your own pace. PacketStream states plainly that purchased balance doesn't expire, which means a $50 top-up bought in a slow month is still sitting there in a busy one.

Payment methods, per PacketStream's FAQ and third-party reviews: credit cards and PayPal are the publicly listed options, with bank transfer possibly approved for larger purchases. A 2026 review from HostAdvice additionally reports Google Pay and Cash App, and card processing through Stripe for Visa, Mastercard and American Express. Payment rails matter more than they sound like they should in this market — plenty of residential providers take crypto and little else.

## What $50 actually buys

Fifty dollars at $1/GB is 50 GB. That's the whole exercise.

Whether 50 GB is a lot depends entirely on what your requests look like. Lightweight jobs — SERP checks, price spot-checks on a few hundred product pages, ad verification, geo-testing a landing page from three countries — tend to move kilobytes to low megabytes each. A 2 KB HTML response is 0.000002 GB. You could run tens of thousands of those on 50 GB.

Heavy jobs eat bandwidth much faster. Pulling full product pages with images and scripts, hitting rate-limited APIs that return fat JSON, downloading media, or running anything through a headless browser where the page loads assets you never look at — those are megabyte-scale per request, sometimes several. At 3 MB per page, 50 GB is roughly 17,000 pages. That sounds like plenty until you're crawling a marketplace with a few million listings on a schedule.

The honest framing: at $1/GB with a flat rate and no tiers, PacketStream is priced for people who don't know their monthly burn yet and don't want to commit to a number to get a decent rate. That's a real advantage over tiered providers, where the $0.70/GB rate on the pricing page requires signing up for a monthly volume you may not hit.

## Where the metered model starts to hurt

Metered bandwidth has one structural problem: cost scales with usage forever. If your scraping volume doubles, your bill doubles. There's no ceiling.

The alternative pricing shape in this market is per-IP with unlimited bandwidth. Instead of buying gigabytes, you buy a fixed number of residential IPs and route as much traffic through them as you want while they're active. The cost is fixed regardless of how many pages you pull — 100 pages or 10,000 pages through one IP, same price.

That model has its own trade-offs. Each IP only lives a few hours to roughly a day, so it's built for session-based work where you need the same address to persist: logged-in flows, cart and checkout testing, account-based tasks where changing IPs mid-session breaks everything. It's a poor fit if your job depends on rotating through thousands of addresses per hour.

But for anyone watching a metered bill climb, the math is worth running. One provider selling exactly this model — 9Proxy — publishes IP packages starting at $24 for 100 IPs, with empty data caps on those sessions. That's less than PacketStream's minimum top-up, and it comes with no per-GB meter running in the background.

## Quick disambiguation: there are two PacketStreams

If you landed on a Korean hosting page showing VPS plans in won, you're looking at a different company that happens to share the name. That PacketStream (`packet.stream`) sells virtual machines, bare metal, block storage and object storage on Korean network infrastructure — its published entry VPS is roughly ₩8,000/month for 1 vCPU, 1 GB RAM, 25 GB SSD and 1 TB of bandwidth, and a "Lite VPS" entry plan has been advertised at $6/month for 1 vCPU, 2 GB RAM, 25 GB SSD, 1 Gbps port and 1 TB of bandwidth.

Nothing to do with residential proxies. Worth knowing, because "packetstream pricing" pulls up both, and the two price pages look nothing alike.

## The per-IP alternative, priced out in full

If you're weighing $1/GB against a fixed IP cost, here's every package the residential proxy platform 9Proxy publishes, including its June 1, 2026 adjustment to IP-based and bundle pricing. GB-based prices were left unchanged in that adjustment.

**IP-based residential packages** (unlimited bandwidth per IP, unused IPs never expire):

| Package | Price per IP | Total |
| --- | --- | --- |
| 100 IPs | $0.24 | $24 —  [Buy 100 IPs with unlimited bandwidth](https://bit.ly/9-Proxy) |
| 500 IPs | $0.144 | $72 —  [Buy 500 IPs](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus | $0.084 | $126 —  [Buy 1,500 IPs (500 free)](https://bit.ly/9-Proxy) |
| 2,500 IPs | $0.084 | $210 —  [Buy 2,500 IPs](https://bit.ly/9-Proxy) |
| 5,000 IPs | $0.072 | $360 —  [Buy 5,000 IPs](https://bit.ly/9-Proxy) |
| 15,000 IPs | $0.048 | $720 —  [Buy 15,000 IPs](https://bit.ly/9-Proxy) |
| 25,000 IPs | $0.035 | $863 —  [Buy 25,000 IPs](https://bit.ly/9-Proxy) |
| 50,000 IPs | $0.029 | $1,438 —  [Buy 50,000 IPs](https://bit.ly/9-Proxy) |

**Business IP packages** (same model, industrial volume):

| Package | Price per IP | Total |
| --- | --- | --- |
| 100,000 IPs | $0.023 | $2,300 —  [Buy 100,000 IPs](https://bit.ly/9-Proxy) |
| 200,000 IPs | $0.021 | $4,140 —  [Buy 200,000 IPs](https://bit.ly/9-Proxy) |
| 500,000 IPs | $0.018 | $8,625 —  [Buy 500,000 IPs](https://bit.ly/9-Proxy) |

**GB-based residential packages** (rotating endpoints, 180-day validity):

| Package | Price per GB | Total | Validity |
| --- | --- | --- | --- |
| 5 GB | $3.00 | $15 —  [Buy the 5 GB starter pack](https://bit.ly/9-Proxy) | 180 days |
| 50 GB + 5 GB bonus | $2.10 | $105 —  [Buy 55 GB](https://bit.ly/9-Proxy) | 180 days |
| 100 GB | $1.50 | $150 —  [Buy 100 GB](https://bit.ly/9-Proxy) | 180 days |
| 200 GB | $1.00 | $200 —  [Buy 200 GB](https://bit.ly/9-Proxy) | 180 days |
| 1,000 GB | $0.80 | $800 —  [Buy 1,000 GB](https://bit.ly/9-Proxy) | 180 days |
| 2,000 GB | $0.75 | $1,500 —  [Buy 2,000 GB](https://bit.ly/9-Proxy) | 180 days |

**Enterprise GB packages** (no expiry):

| Package | Price per GB | Total | Validity |
| --- | --- | --- | --- |
| 3,000 GB | $0.72 | $2,160 —  [Buy 3,000 GB](https://bit.ly/9-Proxy) | Unlimited |
| 6,000 GB | $0.70 | $4,200 —  [Buy 6,000 GB](https://bit.ly/9-Proxy) | Unlimited |
| 10,000 GB | $0.68 | $6,800 —  [Buy 10,000 GB](https://bit.ly/9-Proxy) | Unlimited |

**Bundle packages** (IPs plus bandwidth):

| Bundle | Contents | Price |
| --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 —  [Buy the Starter bundle](https://bit.ly/9-Proxy) |
| Popular | 1,500 IPs + 50 GB | $180 —  [Buy the Popular bundle](https://bit.ly/9-Proxy) |
| Pro | 5,000 IPs + 500 GB | $720 —  [Buy the Pro bundle](https://bit.ly/9-Proxy) |

Two structural differences worth flagging before you compare per-GB rates across these tables.

First, the account is balance-based. IPs purchased in a package don't expire, and GB packages carry at least 180 days of validity — unlimited on the enterprise tiers. That removes the "use it or lose it" pressure that makes monthly-commitment pricing annoying for project work.

Second, the two models have different technical shapes. IP-based plans authenticate through a desktop app that handles local port forwarding, with optional proxy authentication; GB-based plans work straight from the dashboard with username/password or IP whitelisting and rotate automatically per request or per session. If you don't want to install anything, that decision is already made for you. There's a broader breakdown of both models in the platform's own documentation if you want the mechanics rather than the marketing.

## Which one is actually cheaper for you

Strip the brand names out and it comes down to two questions: how much data do you move, and do you need a stable address?

| Your situation | Cheaper structure | Why |
| --- | --- | --- |
| Testing proxies for the first time | Per-IP entry tier | $24 for 100 IPs vs PacketStream's $50 minimum top-up |
| Under ~200 GB/month, bursty usage | PacketStream at $1.00/GB | 9Proxy's small GB packs run $1.50–$3.00/GB; $1.00 flat wins until you pass 200 GB |
| Over ~1 TB/month | 9Proxy GB tiers | $0.80/GB at 1,000 GB and $0.75/GB at 2,000 GB beat a flat $1.00 |
| Long sessions on the same IP, unpredictable bandwidth | Per-IP packages | Unlimited traffic per IP; the bill doesn't move when your crawl gets bigger |
| Highest-volume rotation, hundreds of thousands of IPs | Business IP packages | $0.023/IP at 100,000 IPs; per-GB metering gets expensive fast at that scale |
| You want to offset costs by selling bandwidth | PacketStream | $0.10/GB Packeter program, $5 cashout threshold |

That last row is the one genuine feature PacketStream has that per-IP providers don't: a peer-to-peer network where residential users get paid for the traffic they route. It's not going to fund anything serious — one community-maintained guide estimates passive earnings in the $0–$4/month per device range, with location demand driving most of the variance — but it's a real payout mechanism, not a referral gimmick.

On the reliability side, the numbers that circulate are third-party and should be read that way. Directory listings put 9Proxy at 20M+ residential IPs across 90+ countries with a 97% success rate, and one 2026 review roundup attributes roughly 7M IPs and a 30-minute sticky session cap to PacketStream. Pool size is a weak signal on its own — how fresh the exit nodes are and how rotation is handled matter more in production than a headline count.

## Questions that come up before buying

**Does PacketStream have a free tier?** No. There's a $50 minimum purchase and no subscription, but nothing free. 9Proxy runs a limited new-user trial subject to availability, and you have to say whether you want it on the IP side or the GB side.

**Does my balance expire?** PacketStream says its purchased balance does not expire. 9Proxy's IP packages don't expire and GB packages carry at least 180 days, unlimited on the enterprise tiers. Expiry is a real cost even though it never shows up as a line item — an unused balance on a 30-day clock is money you paid and didn't spend.

**What's the cheapest way to test either one?** Pick the smallest useful unit and measure your own bandwidth per request before committing. Log the bytes for 1,000 representative requests; multiply by your monthly page count; that number decides everything. For most people the answer is under 50 GB, which means the $50 minimum is really a ceiling on your first purchase, not a commitment.

**What payment methods are supported?** PacketStream lists credit cards and PayPal publicly, with bank transfer possible at larger volumes. 9Proxy accepts credit cards, PayPal, crypto (USDT, BTC, ETH, LTC, DOGE and others), bank cards, Alipay, Apple Pay and Google Pay. If you're paying with crypto or a wallet, that difference is decisive.

**Can I get volume discounts on PacketStream?** Not on the retail side — the price is $1.00/GB at every tier, which is unusual and mostly good, since you never pay the "small customer" penalty. Wholesale terms start at $500.

## Picking one without overthinking it

If your job is small-to-medium volume with unpredictable timing, and you like the idea of a flat rate with no tiers and a balance that never dies, PacketStream's $1/GB is a clean deal. Just expect to put in $50 before you route a single request.

If any of the following is true — you want to start for less than $50, you're moving more than a terabyte a month, you need the same IP to hold a session for hours while you pull unlimited data, or you'd rather pay in crypto or via Alipay — the per-IP shape is where the savings are. 👉 [Compare 9Proxy's IP-based and GB-based packages](https://bit.ly/9-Proxy) and you'll see the entry tier costs roughly half of PacketStream's minimum, with the cost locked to the number of IPs instead of the number of gigabytes you burn through.

Either way, decide based on your bandwidth measurement, not on the rate on the landing page. $1/GB and $0.024/IP only become comparable numbers once you know which one your workload multiplies.
