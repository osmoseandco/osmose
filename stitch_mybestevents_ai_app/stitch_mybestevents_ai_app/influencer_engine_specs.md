# MyBestEvents - Influencer Engine Specifications

## 1. Database Schema (partners_influencers)
```json
{
  "id": "auto",
  "name": "string",
  "bio": "text",
  "email": "string",
  "instagram": {
    "username": "string",
    "followers": "number",
    "engagement_rate": "number",
    "profile_url": "url"
  },
  "tiktok": {
    "username": "string",
    "followers": "number",
    "engagement_rate": "number",
    "profile_url": "url"
  },
  "facebook": {
    "page_name": "string",
    "followers": "number",
    "page_url": "url"
  },
  "blog": {
    "url": "url",
    "rss_feed": "url"
  },
  "location": {
    "city": "string",
    "region": "string",
    "country": "string"
  },
  "theme_tags": ["bien-être", "sport", "nutrition", "lifestyle"],
  "content_recent": [
    { "platform": "string", "url": "url", "type": "string", "likes": "number" }
  ],
  "ai_score": {
    "overall": "number",
    "audience_quality": "number",
    "engagement_quality": "number",
    "brand_fit": "number"
  },
  "partnership_status": "available",
  "lead_score": "number"
}
```

## 2. n8n Automation Logic
- **WF_SCRAPE**: Trigger (Form/Scrape) -> Enrichment (IG/TT APIs) -> AI Classification (OpenAI) -> Score Calculation -> DB Upsert.
- **WF_LEAD**: Profile Visit/Click -> Auto Email -> Admin Notification -> CRM Lead Creation.

## 3. AI Scoring Formula
**Score Final = (Audience × 0.4) + (Brand Fit × 0.3) + (Influence × 0.3)**
- **Audience (40%)**: Real followers, growth, engagement.
- **Brand Fit (30%)**: Alignment with the 7 Wellness Spheres.
- **Influence Power (30%)**: Global reach, frequency, virality.