# Twitter/X Post Scraper Agent

> An AI-powered agent built with **n8n**, **OpenAI (GPT-4o-mini)**, and **twitterapi.io** that automatically scrapes Twitter/X posts on any topic and stores them in **Airtable**.

---

## What It Does

- You type any topic (e.g., "AI news", "cricket", "India tech")
- The AI Agent automatically searches Twitter/X for top posts on that topic
- Extracts tweet details: content, author, likes, retweets, views, date, URL
- Saves everything neatly into an Airtable database

---

## Tech Stack

| Tool | Purpose |
|------|----------|
| [n8n](https://n8n.io) | No-code automation & AI Agent orchestration |
| OpenAI GPT-4o-mini | AI brain of the agent |
| [twitterapi.io](https://twitterapi.io) | Twitter/X data scraping API |
| Airtable | Data storage / database |

---

## How It Works

1. User sends a message to the n8n AI Agent (e.g., "Scrape top posts about AI automation")
2. Agent calls the **twitterapi.io** HTTP API with an advanced search query
3. API returns top Twitter/X posts matching the topic
4. Agent extracts fields: `tweet_id`, `text`, `author`, `likes`, `retweets`, `views`, `date`, `url`
5. Data is saved to an **Airtable** base (Twitter Trends table)

---

## Setup Instructions

### 1. twitterapi.io API Key
- Sign up at [twitterapi.io](https://twitterapi.io)
- Copy your API key
- Add it as an HTTP Header credential in n8n (`X-API-Key`)

### 2. Airtable
- Create a base called **Twitter Trends** with fields:
  - `tweet_id`, `url`, `text`, `author`, `likes`, `retweets`, `views`, `date`
- Generate a Personal Access Token from Airtable settings
- Add it as an Airtable credential in n8n

### 3. n8n Agent
- Create a new **AI Agent** in n8n Personal Agents
- Model: `gpt-4o-mini`
- Add an **HTTP Request** tool configured for:
  - URL: `https://api.twitterapi.io/twitter/tweet/advanced_search`
  - Method: `GET`
  - Query params: `queryType=Top`, `query` (auto from AI)
  - Header: `X-API-Key: YOUR_KEY`

---

## Project Background

Built this as a final year B.E. IT student exploring AI automation and no-code tools. Started with n8n and was blown away by how much you can build without writing traditional backend code.

This is just the beginning — planning to extend this into a full social media analytics dashboard!

---

## Author

**Suyash Tamkhane**  
B.E. IT Student | Java Developer | Spring Boot | AI Automation  
[LinkedIn](https://www.linkedin.com/in/suyashtamkhane)

---

*#AI #AIAgent #n8n #OpenAI #Automation #NoCode #TwitterScraper #BuildInPublic #StudentDeveloper*
