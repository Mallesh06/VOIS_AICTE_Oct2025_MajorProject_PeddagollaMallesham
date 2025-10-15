# VOIS_AICTE_Oct2025_MajorProject_PeddagollaMallesham

# 🎬 Netflix Data Analytics using LLMs

## 📌 Project Overview
This project focuses on analyzing the **Netflix dataset** to uncover meaningful insights about the platform's content — such as movies, TV shows, genres, ratings, and release trends.  
It also demonstrates how **Large Language Models (LLMs)** can be integrated to automatically summarize and interpret data insights.

---

## 🎯 Objectives
- Perform **Exploratory Data Analysis (EDA)** on Netflix content data.
- Understand distribution by **type**, **genre**, **country**, and **release year**.
- Visualize insights using **Matplotlib** and **Seaborn**.
- Generate AI-based insights using **LLMs (e.g., Gemini / GPT)**.
- Develop a data-driven summary of Netflix trends.

---

## 🧠 Tech Stack
| Category | Tools / Libraries |
|-----------|------------------|
| Language | Python |
| Environment | Google Colab |
| Data Handling | pandas, numpy |
| Visualization | matplotlib, seaborn |
| AI Integration | google.generativeai / openai (LLMs) |

---

## 📂 Dataset Information
**File:** `Netflix Dataset.csv`

| Column Name | Description |
|--------------|-------------|
| show_id | Unique ID for each show/movie |
| type | Movie or TV Show |
| title | Title of the content |
| director | Director’s name |
| cast | List of actors |
| country | Country of origin |
| date_added | Date when added to Netflix |
| release_year | Original release year |
| rating | Audience rating (e.g., TV-MA, PG) |
| duration | Duration or number of seasons |
| listed_in | Genres / Categories |
| description | Short description |

---

## 📊 Steps Involved

### 1. Data Loading and Exploration
- Loaded the CSV file using pandas.
- Displayed first few rows and dataset structure.
- Checked for missing values and data types.

### 2. Data Cleaning
- Removed duplicate records.
- Converted `date_added` to datetime format.
- Cleaned `duration` column.
- Filled missing values for `country` and `rating`.

### 3. Exploratory Data Analysis (EDA)
- Count of Movies vs TV Shows.
- Content added by year.
- Most common genres.
- Rating distribution.
- Top 10 countries producing Netflix content.

### 4. Visualization
- Created bar charts and count plots using Seaborn and Matplotlib.
- Displayed yearly trends, genre popularity, and content distribution.

### 5. LLM-Based Insights Generation
Used an **LLM** to automatically summarize trends:
> “Based on the Netflix dataset, most content added after 2016 consists of Movies, with the USA and India leading in production. Drama and International Movies are the most popular genres.”

---

## 📈 Key Insights
- Netflix hosts **more Movies** than TV Shows.  
- **USA** and **India** are the leading producers of content.  
- **Dramas**, **Comedies**, and **Documentaries** dominate Netflix genres.  
- Major spike in content additions occurred between **2016–2020**.  
- Ratings like **TV-MA** and **TV-14** are most common.

---

## 🤖 LLM Integration Example
We can integrate a Large Language Model to summarize the EDA automatically.

```python
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

prompt = """
Summarize the key trends from the Netflix dataset:
- More movies or TV shows?
- Top genres and countries?
- Yearly trends?
"""

model = genai.GenerativeModel("gemini-pro")
response = model.generate_content(prompt)
print(response.text)
