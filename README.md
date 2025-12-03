Topic Modeling on Social Media to Understand Shifts in Travel Interests
Overview
This repository contains the code and analysis for a personal research project investigating how online interest in different types of travel changed before, during, and after the COVID-19 pandemic using Reddit data and topic modeling (BERTopic). The project focuses on four travel modes—cruises, camping & hiking, backpacking, and road trips—and combines temporal topic dynamics with sentiment analysis to characterize shifts in preferences over time.​

Project Objectives
Quantify how discussion volume about different travel types evolved from 2018 to September 2023 across 19 travel-related subreddits.

Use BERTopic to derive fine-grained topics and group them into higher-level travel categories (cruise, camping & hiking, backpacking, road trip).

Enrich topic-level trends with sentiment analysis (e.g., VADER) to understand changes in enthusiasm and concerns across periods (pre‑COVID, during‑COVID, post‑COVID).​

Dataset
Source: Reddit posts from 19 travel-related subreddits (e.g., r/travel, r/backpacking, r/CampingandHiking, r/roadtrip, r/cruise), collected between January 2018 and September 2023.

Size: ~700,000 posts with metadata (subreddit, author, timestamp, title/body length).

Temporal segmentation:

Pre‑COVID: Jan 2018 – Dec 2019

During‑COVID: Jan 2020 – Dec 2021

Post‑COVID: Jan 2022 – Sep 2023

Data is assumed to be pre-scraped via the Reddit API or Pushshift and stored as CSV/Parquet files (not included here if redistribution is restricted by Reddit’s terms of service).​

Methods
Topic Modeling:

Sentence embeddings via a transformer-based model.

BERTopic for clustering documents into ~90+ topics, then manual grouping into four travel types based on hierarchical clustering and qualitative inspection.

Temporal Analysis:

Monthly counts and proportions of posts per travel type across the three COVID periods.

Statistical tests (e.g., ANOVA) to assess significance of changes in topic frequency over time.

Sentiment Analysis:

Sentence-level sentiment classification (Positive / Neutral / Negative) using a lexicon- or transformer-based model (e.g., VADER or similar).

Manual sampling to sanity-check sentiment labels for representative posts in each topic group.​
