# Apify Actor Configuration

## Actor
compass/google-maps-reviews-scraper

## Purpose
Automate daily scraping of Google Maps reviews for multiple restaurant and café branches.

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
