# Google-Review-Dataset-for-ETM1005-Assignment3
Google Maps restaurant reviews dataset for ETM1005 A3 data analysis purposes

## 1. Data Collection and Preparation

The **Apify Google Maps Reviews Scraper — Text, Ratings & Replies** is used to collect customer reviews from Google Maps.
Here's the website link:https://console.apify.com

I exported each restaurant's reviews into a separate CSV file. For the competitor restaurants, I configured the scraper to collect up to 100 reviews per restaurant listing.

The original exports contained numerous unnecessary technical columns and, in some cases, additional business-summary records that were not customer reviews.

I cleaned and standardised the datasets to make them suitable for comparative analysis.

### Data Collection and Processing Steps

1. Exported Google Maps customer reviews using Apify.
2. Removed non-review business-summary records.
3. Selected relevant customer-review and restaurant-reply fields.
4. Standardised column names across restaurant datasets.
5. Preserved ratings, review dates and available metadata.
6. Retained original customer reviews in their original languages.
7. Added separate English translation columns for customer reviews.
8. Retained original restaurant-owner replies in their original languages.
9. Added separate English translation columns for restaurant-owner replies.
10. Preserved restaurant names and branch identifiers to distinguish different restaurant locations.
11. Combined the competitor reviews into a single dataset.
12. Merged the Ten Miles Chicken Pot reviews with the competitor dataset to produce the final comparison dataset.

The final combined dataset contains **722 review records and 18 columns**, covering Ten Miles Chicken Pot and seven competitor restaurant listings.

Further data-quality verification may be required before conducting statistical or text-based analysis.

## 2. Dataset Column Structure

The final combined CSV contains the following 18 columns:

- `restaurant`
- `review_id`
- `review_date`
- `rating`
- `reviewer_name`
- `review_text`
- `review_text_english`
- `review_language`
- `food_rating`
- `service_rating`
- `atmosphere_rating`
- `price_per_person`
- `has_owner_reply`
- `owner_reply`
- `owner_reply_english`
- `owner_reply_language`
- `owner_reply_date`
- `review_url`

### Important Column Descriptions

| Column | Description |
|---|---|
| `restaurant` | Identifies the restaurant and its branch or location. |
| `review_text` | Original customer review, preserving its original language. |
| `review_text_english` | English version of the customer review for analysis. |
| `owner_reply` | Original response from the restaurant owner or management. |
| `owner_reply_english` | English version of the restaurant-owner response. |

Some customer reviews and restaurant replies were originally written in Chinese, Malay, Japanese or a mixture of languages. I prepared English translations in separate columns while preserving the original text.

Missing reviews and restaurant replies are left blank rather than replaced with artificial content.

### Restaurant and Branch Identification

I retained the `restaurant` column in the combined dataset to distinguish reviews from different restaurants and locations.

**Chicken Claypot House (鸡煲之家)** has two branches included in the final dataset:

- **Chicken Claypot House — Sunway Pyramid**
- **Chicken Claypot House — SS2**

Although these locations belong to the same restaurant brand, I treated them as separate restaurant listings because their locations and customer experiences may differ.

**Hong Kong Chicken Hot Pot** has two separately named CSV files:

- **Hong Kong Chicken Hot Pot — 26, Jalan SS2/67, Petaling Jaya**
- **Hong Kong Chicken Hot Pot — 86, Jalan SS2/60, Petaling Jaya**

Only the listing at **86, Jalan SS2/60** is included in the final combined dataset. The other CSV is retained separately for reference.

The relationship between the two Hong Kong Chicken Hot Pot listings has not been independently verified.

I preserved location information in the restaurant identifiers and individual CSV filenames to avoid confusing different locations or incorrectly grouping their reviews.

## 3. Important Dataset Files

| File | Description |
|---|---|
| `ten_miles_chicken_pot_reviews.csv` | Contains 22 customer reviews from the target restaurant, Ten Miles Chicken Pot. |
| `competitor_restaurant_google_reviews.csv` | Contains 700 reviews from seven competitor restaurant listings. |
| `final_restaurant_comparison_google_reviews.csv` | Final combined dataset containing 722 reviews from eight restaurant listings, with Ten Miles Chicken Pot listed first. |

The final combined dataset is intended for comparative customer-experience analysis. The individual restaurant datasets are retained for reference and data verification.
