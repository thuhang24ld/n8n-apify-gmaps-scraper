# Apify Actor Configuration

## Actor
compass/google-maps-reviews-scraper

## Purpose
Automate daily scraping of Google Maps reviews for multiple restaurant and café branches. [image](https://github.com/thuhang24ld/n8n-apify-gmaps-scraper/blob/main/image/apify_actor.png?raw=true)

## Extracted Fields
- reviewerName
- reviewText
- stars
- reviewUrl
- publishedDate
- responseFromOwner
- totalReviewerReviews

## Output Formats
- JSON
- CSV

## Integration
The scraped data is processed through an n8n workflow for:
- review monitoring
- low-rating detection
- Google Sheets storage
- Discord alert notifications
