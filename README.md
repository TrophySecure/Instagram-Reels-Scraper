[Instagram Reels Scraper](https://apify.com/scraply/instagram-reels-scraper?fpr=data)

## Instagram Reels Scraper

The Instagram Reels Scraper is a production-ready Instagram Reels scraper tool that extracts structured metadata from public Reels at scale. It solves the pain of manual collection by providing a reliable Instagram Reels data extractor for marketers, analysts, and developers — perfect for trend tracking, content benchmarking, and research. Use it as a bulk Instagram Reels scraper in workflows for analytics, enrichment, or automation, and export clean datasets for your BI stack.

## What data / output can you get?

Here are the main fields this Instagram Reels metadata scraper returns in the dataset. Values below are real examples taken from public reels.

| Data type | Description | Example value |
| --- | --- | --- |
| reel_id | Primary identifier (pk or id) | "3727980973477364718" |
| shortcode | Reel shortcode used in URLs | "DO8cvGViIPu" |
| reel_url | Canonical URL to the reel | "[https://www.instagram.com/reel/DO8cvGViIPu/](https://www.instagram.com/reel/DO8cvGViIPu/)" |
| author_username | Reel author’s username | "alnassr" |
| author_full_name | Author’s full name | "نادي النصر السعودي" |
| author_is_verified | Verified badge flag | true |
| caption_text | Full caption text | "🎥 On the 95th Saudi National Day..." |
| like_count | Total likes | 1258268 |
| comment_count | Total comments | 12381 |
| play_count | Total plays | 37796913 |
| video_url | Direct video asset URL | "[https://scontent-iad3-2.cdninstagram.com/o1/](https://scontent-iad3-2.cdninstagram.com/o1/)..." |
| thumbnail_url | Thumbnail image URL | "[https://scontent-iad3-2.cdninstagram.com/v/t51.82787-15/](https://scontent-iad3-2.cdninstagram.com/v/t51.82787-15/)..." |
| taken_at_iso | ISO timestamp | "2026-...T..." |
| hashtags | Hashtags parsed from caption | [] |
| mentions | @mentions parsed from caption | [] |
| audio_title | Audio display title | "Original audio" |
| audio_artist | Audio creator/artist (if available) | "alnassr" |

Notes:

- Additional outputs include media_type, video_duration, view_count, tagged_users, coauthor_usernames, and compliance-friendly flags like is_paid_partnership and has_audio.
- Full raw reel JSON is preserved in reel_data for advanced use.
- Export your dataset to JSON, CSV, or Excel via Apify.

## Key features

- 🔁 Robust proxy fallback
Automatically starts direct, then escalates to datacenter and residential proxies if Instagram rejects requests. Clear logging and retries keep your runs stable at scale.
- 🧩 Rich reel metadata
Captures caption_text, hashtags/mentions, video_url, thumbnail_url, play_count, like_count, comment_count, audio_title/artist, tagged_users, coauthor_usernames, and more.
- 📦 Bulk scraping at scale
Works as a Bulk Instagram Reels scraper — set maxReels per profile and process large lists of usernames, profile URLs, or shortcodes without manual effort.
- 💻 Developer-friendly
Use via the Apify REST API or SDKs in your Instagram Reels scraper Python or Node.js pipelines. Ideal for building an Instagram Reels scraper API into data workflows.
- 🔌 Automation & integrations
Trigger via webhooks and schedule runs. Export to Sheets, CSV/Excel, or pipe JSON to warehouses and ETL tools (Make, Zapier, Airbyte, etc.).
- 🔒 Public data only
A compliance-aware Instagram Reels profile scraper designed for public content — no login required for public profiles. Great alternative to risky Instagram Reels scraping Chrome extension approaches.
- 📊 Analytics-ready output
Flattened fields plus full reel_data ensure both quick analysis and deep-dive research, making it a dependable Instagram Reels analytics scraper.
- 🛠️ Production reliability
Clear status logs, HTTP error handling, and proxy rotation help maintain consistent runs for ongoing monitoring and benchmarking.

## How to use Instagram Reels Scraper - step by step

1. Create or log in to your Apify account.
2. Open the Instagram Reels Scraper actor.
3. Add input data:

- Paste Instagram profile URLs (e.g., [https://www.instagram.com/username](https://www.instagram.com/username)).
- Or provide usernames (e.g., username or @username).
- You can also enter reel/post shortcodes (e.g., CxYz123AbCd) or full reel/post URLs — the actor normalizes these to the correct profile.
4. Configure settings:

- maxReels: limit how many reels to collect per profile.
- proxyConfiguration: choose proxies if needed (the actor will fall back automatically when blocked).
5. Start the run:

- The actor resolves each input to a username and fetches reels with pagination.
- If a direct connection is rejected, it falls back to datacenter then residential proxies with retries.
6. Monitor progress in logs and run details.
7. Download results:

- Export datasets to JSON, CSV, or Excel, or pull via the Apify API into your apps and dashboards.

Pro Tip: Chain this with an external Instagram Reels video downloader step if you need to store media files — this actor provides video_url for compliant pipelines.

## Use cases

| Use case name | Description |
| --- | --- |
| Marketing analytics – reel benchmarking | Compare play_count, like_count, and captions across competitors to identify winning hooks and creative patterns. |
| Influencer research – talent tracking | Track author_username, verification, collaborations (coauthor_usernames), and engagement to rank creators in your niche. |
| Content strategy – hashtag/caption mining | Use hashtags, mentions, and caption_text to cluster topics and inform content briefs. |
| Brand monitoring – tagged UGC capture | Collect tagged_users and mentions to surface UGC and partnerships for reporting. |
| Data engineering – API pipeline | Integrate this Instagram Reels scraper API with Python SDKs to populate warehouses for weekly KPI dashboards. |
| Academic / market research | Export clean JSON/CSV for reproducible studies on media trends, audio usage, or posting cadence. |
| Creative QA – media checks | Use thumbnail_url and video_url references to audit creative variants in content ops workflows. |

## Why choose Instagram Reels Scraper?

Built for precision, automation, and reliability — without the instability of browser extensions or ad‑hoc scripts.

- ✅ Accurate field coverage: Captures the key metadata you need for analysis and enrichment.
- 🌍 No login for public content: A safe Instagram Reels scraper without login for public profiles.
- ⚡ Scales with you: Handles batch inputs and maxReels limits for large panels and long‑running monitors.
- 💻 Developer access: Works seamlessly with Apify’s API and SDKs for Instagram Reels scraper Python or Node pipelines.
- 🧩 Easy integrations: Export to JSON/CSV/Excel and orchestrate with Make/Zapier or your ETL.
- 🛡️ Compliance-first: Focused on public data; respects platform responses with robust proxy fallback.
- 💸 Cost-effective vs. fragile alternatives: Production infrastructure beats DIY maintenance and unreliable plugins.

Bottom line: a dependable Instagram Reels URL extractor and metadata engine for teams that need repeatable, analysis-ready data.

## Is it legal / ethical to use Instagram Reels Scraper?

Yes — when used responsibly. This actor extracts publicly available information and does not access private profiles or authenticated data.

Guidelines to follow:

- Collect public content only and avoid private/profile-restricted data.
- Ensure your use complies with applicable laws (e.g., GDPR/CCPA) and platform terms.
- Apply data minimization, secure storage, and retention policies.
- Consult your legal team for edge cases and jurisdiction-specific requirements.

## Input parameters & output format

Example JSON input

```
{
  "urls": [
    "https://www.instagram.com/mrbeast",
    "cristiano"
  ],
  "maxReels": 10,
  "proxyConfiguration": {
    "useApifyProxy": false
  }
}
```

Input fields

- urls (array)

- Description: List of Instagram profile URLs (e.g., [https://www.instagram.com/username](https://www.instagram.com/username)), usernames (e.g., username), or shortcodes (e.g., CxYz123AbCd). Supports full URLs, @username, username, reel shortcodes, and post shortcodes.
- Default: none
- Required: no
- maxReels (integer)

- Description: Maximum number of reels to scrape per profile
- Default: 10 (min: 1, max: 1000)
- Required: no
- proxyConfiguration (object)

- Description: Choose which proxies to use. If Instagram rejects the proxy, a residential proxy will be used as a fallback.
- Default: {"useApifyProxy": false}
- Required: no

Example JSON output

```
{
  "username": "cristiano",
  "scraped_at": 1758818318.2891665,
  "sort_order": "newest",
  "max_comments": 50,
  "reel_id": "3727980973477364718",
  "shortcode": "DO8cvGViIPu",
  "reel_url": "https://www.instagram.com/reel/DO8cvGViIPu/",
  "author_username": "alnassr",
  "author_full_name": "نادي النصر السعودي",
  "author_is_verified": true,
  "author_profile_pic_url": "https://scontent-iad3-2.cdninstagram.com/v/t51.2885-19/498707137_18506209855018981_4274309452484658175_n.jpg",
  "caption_text": "🎥\nOn the 95th Saudi National Day 🇸🇦\nCristiano Ronaldo shares a message with the Saudi people 💚",
  "like_count": 1258268,
  "comment_count": 12381,
  "play_count": 37796913,
  "view_count": 0,
  "video_duration": 47.5,
  "media_type": 2,
  "video_url": "https://scontent-iad3-2.cdninstagram.com/o1/v/t2/f2/m86/AQPoU7c34SRUiZGbnIlMHGjjNlE2vEINoSOB1D9xT8K3LSVWseTYD1eCY5MlfT6a....mp4",
  "thumbnail_url": "https://scontent-iad3-2.cdninstagram.com/v/t51.82787-15/553463806_18529709899018981_4493947018023838808_n.jpg",
  "taken_at": 1758630037,
  "taken_at_iso": "2026-...T...",
  "hashtags": [],
  "mentions": [],
  "hashtags_count": 0,
  "mentions_count": 0,
  "audio_title": "Original audio",
  "audio_artist": "alnassr",
  "tagged_users": [
    "cristiano"
  ],
  "tagged_users_count": 1,
  "coauthor_usernames": [
    "cristiano"
  ],
  "coauthor_count": 1,
  "is_paid_partnership": false,
  "has_audio": true,
  "can_viewer_save": true,
  "reel_data": {
    "media": {
      "pk": "3727980973477364718",
      "code": "DO8cvGViIPu",
      "user": {
        "username": "alnassr",
        "is_verified": true
      },
      "video_versions": [
        {
          "url": "https://scontent-iad3-2.cdninstagram.com/o1/v/t2/f2/m86/AQPoU7c34SRUiZGbnIlM....mp4"
        }
      ]
    }
  }
}
```

Notes:

- Fields like hashtags, mentions, audio_title, audio_artist, tagged_users, and coauthor_usernames may be empty if not present.
- Each item includes reel_data with the raw JSON for advanced processing.

## FAQ

### Do I need to log in to use this Instagram Reels Scraper?

No. It works on public profiles without login. The actor fetches public endpoints and includes smart proxy fallback to keep requests reliable.

### Can I use this with Python or via an API?

Yes. Access the dataset through Apify’s REST API or integrate with the Apify SDKs in your Instagram Reels scraper Python pipelines and automation workflows.

### How many reels can I scrape per profile?

You can control this with the maxReels input (1 to 1000, default 10). The actor paginates through reels and stops when your limit is reached or when no more items are available.

### Does it download videos?

It doesn’t download files. Instead, it returns video_url so you can connect a separate Instagram Reels video downloader step if you need to store media.

### Can I input reel URLs or shortcodes instead of usernames?

Yes. You can provide profile URLs, usernames, @usernames, reel shortcodes, post shortcodes, and full reel/post URLs. The actor normalizes these to the correct profile automatically.

### What metrics are included for analytics?

You’ll get play_count, like_count, comment_count, video_duration, timestamps, caption_text, hashtags/mentions, tagged_users, and audio metadata — ideal for dashboards and analysis.

### Is it better than a scraping Chrome extension?

For reliability and scale, yes. This Instagram Reels scraper tool runs in the cloud with proxy fallback and exports to JSON/CSV/Excel — no fragile browser setup required.

### Is scraping Instagram Reels legal?

Yes, when done responsibly with public data and in compliance with platform terms and local laws. Avoid private data, follow GDPR/CCPA where applicable, and consult your legal team for specific use cases.

## Final thoughts

This Instagram Reels Scraper is built to turn public Reels into structured, analytics-ready data. With robust proxy handling, clean fields, and easy exports, it supports marketers, developers, analysts, and researchers at scale. Plug it into your Instagram Reels scraper API or Python pipeline, automate exports, and start turning Reels metadata into actionable insights.