[Instagram Reels Scraper](https://apify.com/instaprism/instagram-reels-scraper?fpr=data)

# Instagram Reels Scraper - Export Reels with Views & Engagement 2026

Extract Reels from any public Instagram account with complete engagement metrics. Get view counts, likes, comments, duration, and engagement rates. Perfect for analyzing viral video content and understanding what works on Instagram.

## No Login Required

**Your Instagram account stays safe.** This Actor:

- Does NOT require your Instagram login or cookies
- Uses our own infrastructure to fetch data
- Zero risk of account suspension for you
- Works with any public Instagram profile

Unlike browser extensions or tools that use your account, we handle all scraping server-side. Your credentials are never needed.

## Important: Processing Time

**This Actor uses a distributed scraping architecture.** Here's what to expect:

| Data Size | First Results | Complete Results |
| --- | --- | --- |
| 20 Reels | 2-3 min | 3-5 min |
| 50 Reels | 3-5 min | 5-10 min |
| 100+ Reels | 5-10 min | 10-20 min |

**Why does it take time?**

- Instagram has strict rate limits to prevent spam
- We use multiple proxy servers worldwide to stay undetected
- Each Reel requires fetching detailed engagement data

**Don't worry about timeouts!** Our streaming mode saves results every 60 seconds. Even if Apify times out after 24h, you'll have all the data collected up to that point.

## What You Get

- **Reel URL** - Direct link to the Reel
- **Reel ID** - Unique identifier
- **Views Count** - Number of views (plays)
- **Likes Count** - Number of likes
- **Comments Count** - Number of comments
- **Duration** - Length in seconds
- **Caption** - Reel description text
- **Engagement Rate** - Calculated engagement percentage
- **Published Date** - When the Reel was posted

## Why Reels Matter

Reels are Instagram's highest-reach content format. They get:

- 22% more engagement than regular videos
- 2x more reach than photo posts
- Prime algorithm visibility

Understanding what makes Reels go viral is crucial for Instagram success.

## Input

| Parameter | Type | Required | Default | Description |
| --- | --- | --- | --- | --- |
| `username` | String | Yes | - | The Instagram username to scrape Reels from (without the @ symbol) |
| `limit` | Integer | No | 50 | Maximum number of Reels to extract |

### Example Input

```
{
    "username": "garyvee",
    "limit": 100
}
```

## Output

| Field | Type | Example | Description |
| --- | --- | --- | --- |
| `position` | Integer | 1 | Position in the Reels feed (1 = most recent) |
| `reelId` | String | "3245678901234567890" | Unique Instagram Reel ID |
| `url` | String | "[https://instagram.com/reel/ABC123/](https://instagram.com/reel/ABC123/)" | Direct URL to the Reel |
| `views` | Integer | 2500000 | Number of views |
| `likes` | Integer | 150000 | Number of likes |
| `comments` | Integer | 5000 | Number of comments |
| `duration` | Integer | 30 | Duration in seconds |
| `caption` | String | "Check this out! #viral" | Reel caption/description |
| `engagementRate` | String | "6.20" | Engagement percentage (likes+comments/views*100) |
| `publishedAt` | String | "2026-01-15T10:30:00.000Z" | When the Reel was posted |
| `scrapedFrom` | String | "garyvee" | Source account username |
| `scrapedAt` | String | "2026-01-15T12:00:00.000Z" | When the data was scraped |

### Example Output

```
[
    {
        "position": 1,
        "reelId": "3245678901234567890",
        "url": "https://www.instagram.com/reel/ABC123/",
        "views": 2500000,
        "likes": 150000,
        "comments": 5000,
        "duration": 30,
        "caption": "The secret to success nobody talks about... #entrepreneur #mindset",
        "engagementRate": "6.20",
        "publishedAt": "2026-01-15T10:30:00.000Z",
        "scrapedFrom": "garyvee",
        "scrapedAt": "2026-01-15T12:00:00.000Z"
    },
    {
        "position": 2,
        "reelId": "3245678901234567889",
        "url": "https://www.instagram.com/reel/XYZ789/",
        "views": 1800000,
        "likes": 95000,
        "comments": 3200,
        "duration": 45,
        "caption": "Stop making excuses and start making moves #motivation",
        "engagementRate": "5.46",
        "publishedAt": "2026-01-14T15:00:00.000Z",
        "scrapedFrom": "garyvee",
        "scrapedAt": "2026-01-15T12:00:01.000Z"
    }
]
```

## Use Cases

- **Competitor Analysis** - See what Reels perform best for competitors. Identify winning formats and topics.
- **Content Research** - Find viral Reel formats in your niche. Understand optimal video length and style.
- **Influencer Vetting** - Verify real engagement on Reels before signing partnerships.
- **Trend Detection** - Spot emerging content trends by analyzing high-performing Reels.
- **Benchmarking** - Calculate average engagement rates to set realistic KPIs for your content.

## Streaming Mode (Auto-Save)

This Actor uses **streaming mode** to protect your data:

- Results saved to dataset every 60 seconds
- No data loss even on timeout or interruption
- Monitor progress in real-time via logs
- Partial results always available

## Integrations

Export your data to:

- **Google Sheets** - Direct integration, auto-sync results
- **Zapier / Make (Integromat)** - Trigger workflows when scrape completes
- **Webhooks** - Get real-time notifications
- **API** - Programmatic access via Apify API
- **Download** - JSON / CSV / Excel files

## FAQ

### Why is my scrape taking so long?

Instagram limits how fast data can be fetched. Each Reel requires fetching detailed metrics. Our distributed architecture maximizes speed while staying undetected.

### Can I scrape Reels from private accounts?

No, this Actor only works with public Instagram profiles. Private accounts require login credentials which we don't support.

### What if the Actor times out?

Your data is safe! Streaming mode saves results every 60 seconds to the Apify dataset. If the run times out, you can download whatever was collected.

### How is engagement rate calculated?

Engagement Rate = (Likes + Comments) / Views * 100. This gives you a percentage showing how engaging the Reel was relative to its reach.

### Can I get the actual video files?

We provide the Reel URL. Downloading the video file itself would require additional tools - we focus on extracting the metadata and metrics.

### What's a good engagement rate for Reels?

Benchmarks vary by niche, but generally:

- 1-3% = Average
- 3-6% = Good
- 6%+ = Excellent

### How far back can I scrape?

Instagram provides access to recent Reels. Very old Reels may not be accessible, but typically the most recent 100-200+ Reels are available.

### How often can I run this?

As often as you need. Each run is independent. For tracking Reel performance over time, set up scheduled runs via Apify.

## Keywords

Instagram Reels scraper, export Instagram Reels, scrape Instagram Reels, Instagram video analytics, Instagram Reels engagement, Instagram content analysis, Instagram viral video research, Instagram Reels metrics, Instagram marketing tool, Instagram data extraction

## Need Custom Solutions?

Looking for **custom scraping**, **higher limits**, or **dedicated infrastructure**?

📩 **Contact us:**

- **Telegram:** [@taskforceorange](https://t.me/taskforceorange)
- **Website:** [social-swarm.com](https://social-swarm.com)

We offer:

- Custom actor development
- Enterprise-grade scraping solutions
- Dedicated proxy infrastructure
- White-label integrations
- Priority support

---

*Built with ❤️ by the InstaPrism team*