[Instagram Reels Scraper](https://apify.com/charlsondou/Instagram-Reels-Scraper?fpr=data)

## Overview

Instagram Reels Comments Scraper API is a lightweight Apify Actor for collecting structured data from Instagram reels, posts, and public profiles. Provide one or more Instagram usernames or reel/post URLs and get JSON records with captions, media URLs, engagement counts, share counts when available, and visible comments.

This Actor is a hosted API wrapper. It sends your input to a maintained backend endpoint and saves the returned items into your Apify dataset.

## Features

- Scrape direct Instagram reel/post URLs
- Scrape recent reels/posts from one or more public profile usernames
- Collect captions, hashtags, mentions, owner details, timestamps, dimensions, thumbnails, and video URLs
- Collect likes, comments count, play/view count, and share count when visible
- Collect visible comments with a configurable per-post limit
- Supports multiple usernames or URLs in one run
- Outputs clean structured JSON ready for analytics, automation, n8n, Make, Airtable, Google Sheets, or AI workflows

## For Apify Users

Run this Actor with your normal Apify account or Apify API token. You do not need to provide the backend API key. The Actor owner configures private backend environment variables. Users do not need to provide them.

## Actor Owner Configuration

Before publishing or running this Actor as the owner, set these environment variables in the Apify Actor settings:

```
ZEABUR_URL=your_private_backend_endpoint
API_KEY=your_private_backend_api_key
# Optional internal troubleshooting only:
INCLUDE_DEBUG=false
```

`API_KEY` is not an Apify user token. It is the private key used by this Actor to call your private backend API. Apify users run the Actor with their normal Apify API token and never see this value.

## Input Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `username` | Array | Instagram usernames, profile URLs, or direct reel/post URLs. You can mix accounts and URLs. |
| `reelCount` | Integer | Number of recent reels/posts to fetch per profile. Direct URLs return one item. |
| `commentsLimit` | Integer | Maximum visible comments to collect per reel/post. Use lower values for faster runs. |
| `onlyPostsNewerThan` | String | Optional date filter. Supports `YYYY-MM-DD`, ISO timestamps, or relative values like `7 days`, `2 weeks`, `3 months`. |
| `skipPinnedPosts` | Boolean | Skip pinned posts when profile discovery can identify them. |
| `maxConcurrency` | Integer | Maximum number of items processed in parallel by the backend API. |

## Example Input

Scrape two recent reels from multiple profiles:

```
{
  "username": ["cla.x.fitness", "aiflowtime"],
  "reelCount": 2,
  "commentsLimit": 50,
  "skipPinnedPosts": true
}
```

Scrape direct reel URLs:

```
{
  "username": [
    "https://www.instagram.com/reel/DWltAaSAAYL/",
    "https://www.instagram.com/p/DX0zV3lAQWM/"
  ],
  "commentsLimit": 100
}
```

Mix profiles and direct URLs:

```
{
  "username": [
    "cla.x.fitness",
    "https://www.instagram.com/reel/DWltAaSAAYL/",
    "humansofny"
  ],
  "reelCount": 1,
  "commentsLimit": 50
}
```

## Output Data

Each dataset item represents one Instagram reel/post.

| Field | Description |
| --- | --- |
| `id` | Instagram media ID when available |
| `type` | Media type, usually `Video` |
| `shortCode` | Instagram shortcode |
| `caption` | Post caption text |
| `hashtags` | Hashtags extracted from the caption |
| `mentions` | Mentioned usernames extracted from the caption |
| `url` | Canonical Instagram post/reel URL |
| `commentsCount` | Public comments count when available |
| `dimensionsHeight` / `dimensionsWidth` | Media dimensions |
| `images` | Thumbnail/preview image URLs |
| `videoUrl` | Direct video media URL when accessible |
| `likesCount` | Public like count when available |
| `sharesCount` | Share count when visible to the backend session |
| `timestamp` | Post timestamp |
| `ownerFullName` | Creator display name |
| `ownerUsername` | Creator username |
| `ownerId` | Instagram owner ID |
| `productType` | Instagram product type, for example `clips` |
| `videoDuration` | Video duration in seconds |
| `inputUrl` | Original input URL used for this item |
| `firstComment` | First collected comment text when available |
| `latestComments` | Array of collected visible comments |
| `latestCommentsFetchedCount` | Number of comments returned |
| `commentsLimit` | Requested per-post comments limit |
| `displayUrl` | Main display image URL |
| `videoViewCount` | View count when available |
| `videoPlayCount` | Play count when available |
| `childPosts` | Child posts for carousel-like data when available |
| `status` | Processing status |
| `processedAt` | Backend processing timestamp |

## Example Output

```
{
  "id": "3887958181485282700",
  "type": "Video",
  "shortCode": "DX0zV3lAQWM",
  "caption": "Post caption text...",
  "hashtags": [],
  "mentions": [],
  "url": "https://www.instagram.com/p/DX0zV3lAQWM/",
  "commentsCount": 40,
  "images": ["https://...jpg"],
  "videoUrl": "https://...mp4",
  "likesCount": 1157,
  "sharesCount": 11,
  "timestamp": "2026-05-02T05:55:03.000Z",
  "ownerFullName": "Creator name",
  "ownerUsername": "creator_username",
  "ownerId": "123456789",
  "productType": "clips",
  "videoDuration": 104,
  "inputUrl": "https://www.instagram.com/p/DX0zV3lAQWM/",
  "firstComment": "Nice post",
  "latestComments": [
    {
      "id": "18000000000000000",
      "text": "Nice post",
      "ownerUsername": "commenter",
      "owner": {
        "is_verified": false,
        "username": "commenter"
      }
    }
  ],
  "latestCommentsFetchedCount": 1,
  "commentsLimit": 50,
  "displayUrl": "https://...jpg",
  "videoViewCount": 10000,
  "videoPlayCount": 10000,
  "childPosts": [],
  "status": "success",
  "processedAt": "2026-05-03T12:00:00.000000+00:00"
}
```

## How It Works

1. Add Instagram usernames, profile URLs, or direct reel/post URLs.
2. The Actor forwards the request to the hosted Instagram scraping API.
3. The backend resolves recent posts, loads visible comments, and enriches each record.
4. The Actor stores each returned item in the Apify dataset.

## Performance Tips

For many accounts, avoid very large runs in one request. Start with:

```
{
  "username": ["account1", "account2", "account3"],
  "reelCount": 1,
  "commentsLimit": 20
}
```

Increase `reelCount` and `commentsLimit` gradually. Comments collection is the slowest part because Instagram often requires browser-like scrolling to load more comments.

## Notes & Limitations

- Works best with public Instagram profiles and public reels/posts.
- Private, restricted, removed, or region-limited content may not be accessible.
- Engagement numbers can change over time and may differ from what you see in the Instagram app.
- Share counts are returned only when visible to the backend session and may be unavailable for some posts.
- Comments are visible comments loaded by the backend session, not guaranteed to be every comment on very large posts.
- Direct media URLs may expire because Instagram CDN URLs are time-limited.

## Use Cases

- Influencer and creator research
- Reels engagement monitoring
- Comment mining and keyword research
- Social media analytics dashboards
- Competitor content tracking
- Lead generation and community analysis
- Feeding Instagram post data into AI workflows

## SEO Keywords

Instagram Reels Scraper, Instagram Comments Scraper, Instagram Post Scraper, Instagram Profile Reels API, Instagram Engagement Data, Instagram Shares Count Scraper, Instagram JSON API Alternative, Instagram Social Media Analytics

## Disclaimer

Use this Actor responsibly and only for lawful purposes. Instagram may restrict automated collection of data in its terms of service. This Actor is intended for collecting accessible Instagram post/profile data for analytics, research, and automation workflows. The developer is not responsible for misuse.