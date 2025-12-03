# Topic Modeling on Social Media to Understand Shifts in Travel Interests

## Overview

This repository contains the code and analysis for a personal research project investigating how online interest in different types of travel changed before, during, and after the COVID-19 pandemic using Reddit data and topic modeling (BERTopic). The project focuses on four travel modes—cruises, camping & hiking, backpacking, and road trips—and combines temporal topic dynamics with sentiment analysis to characterize shifts in preferences over time.

## Project Objectives

- Quantify how discussion volume about different travel types evolved from 2018 to September 2023 across 19 travel-related subreddits.
- Use BERTopic to derive fine-grained topics and group them into higher-level travel categories (cruise, camping & hiking, backpacking, road trip).
- Enrich topic-level trends with sentiment analysis to understand changes in enthusiasm and concerns across periods (pre‑COVID, during‑COVID, post‑COVID).

## Dataset

- Source: Reddit posts from 19 travel-related subreddits (for example, `r/travel`, `r/backpacking`, `r/CampingandHiking`, `r/roadtrip`, `r/cruise`), collected between January 2018 and September 2023.
- Size: ~700,000 posts with metadata (subreddit, author, timestamp, title/body length).
- Temporal segmentation:
  - Pre‑COVID: Jan 2018 – Dec 2019  
  - During‑COVID: Jan 2020 – Dec 2021  
  - Post‑COVID: Jan 2022 – Sep 2023  

Note: Data collection relied on the Reddit API / Pushshift; raw dumps may not be redistributed publicly due to Reddit’s terms of service.

## Methods

### Topic Modeling

- Clean and preprocess post text (basic normalization, stopword removal where appropriate).
- Encode posts with a sentence-transformer model.
- Apply BERTopic to cluster documents into ~90+ topics.
- Inspect the hierarchical topic structure and manually group topics into four travel types:
  - Cruise
  - Camping & Hiking
  - Backpacking
  - Road Trip

### Temporal and Statistical Analysis

- Compute monthly counts and proportions of posts for each travel type.
- Aggregate by pre‑, during‑, and post‑COVID periods.
- Use statistical tests (for example, ANOVA) to assess whether changes in topic frequency across periods are significant.

### Sentiment Analysis

- Assign sentiment labels (Positive / Neutral / Negative) to posts using a sentiment model (for example, VADER or a transformer-based classifier).
- Manually audit samples for each class and travel type to check label quality.
- Track how the distribution of sentiments changes over time for each travel type.

## Key Findings

- Cruise and backpacking discussions decrease sharply during COVID and rebound strongly afterward, surpassing pre‑pandemic volumes and showing more family- and higher-budget–oriented language.
- Camping & hiking activity rises during the pandemic and then falls post‑COVID, with surviving discussions skewing toward more specialized, gear-focused topics.
- Sentiment around cruises becomes more neutral/negative during the pandemic but turns more positive post‑COVID, in line with reports of strong recovery in cruise demand.

## Repository Structure

