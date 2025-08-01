### Primary Sensitivity Analysis Tool:
***VADER (Valence Aware Dictionary for sEntiment Reasoning)***

Best suited for: Social media posts, YouTube comments, and other informal or short-form text.

**Pros:**
1. Extremely fast and lightweight
2. Built into the NLTK library
3. Handles slang, emojis, punctuation, and capitalization effectively

**Cons:** 
- Lexicon-based approach limits its ability to understand sarcasm, irony, or complex contextual nuance
- Classifies comments in foreign languages as neutral

**How it works:**
VADER assigns each comment a compound sentiment score ranging from -1 (most negative) to +1 (most positive). 

**Interpretation:**
- Positive sentiment: score > 0.05
- Negative sentiment: score < -0.05
- Neutral sentiment: between -0.05 and 0.05

Higher absolute values indicate stronger sentiment intensity.

### Data Collection Challenges

Our initial plan was to scrape data from Twitter and Reddit. However, several limitations led us to reconsider:

**Twitter:**
    - Access to the Twitter API has become prohibitively expensive, making large-scale data collection unfeasible for this project.

**Reddit:**
- The two main Reddit APIs have significant constraints:
  - PRAW (Python Reddit API Wrapper) is still functional but only supports scraping from the top, hot, and new posts. It does not allow filtering by custom timeframes and has a hard limit of 1,000 posts per query.
  - Pushshift, which previously allowed time-based filtering and more flexible querying, has been offline since 2023, making it unavailable for use.

**Final Approach – YouTube:**
- Due to these limitations, we shifted our focus to YouTube comments, which offered an accessible and rich source of user-generated content. This allowed us to collect timely political discourse data with fewer restrictions on volume or timeframe.

### 2016 Datasets

Observation: Number of observations differed greatly. After data cleaning, there were 30,269 total observations for the democratic dataframe, and there were only 1,614 total observations for the republican dataframe.

***Data Cleaning and Processing Observations***

**Deduplication:** Retained only one comment per user to reduce repetition and bias in sentiment distribution. Many users also reposted the same or similar comments, leading to a high volume of duplicates that require removal or consolidation. **Thread Misuse:** Replies are often posted as new top-level comments rather than nested replies, disrupting the natural conversational flow.

### Alternative Model - HuggingFace

**Hugging Face Sentiment Analysis:**
Unlike VADER, which produces a numerical compound sentiment score ranging from -1 to 1, Hugging Face’s sentiment-analysis pipeline provides:
- A sentiment label: 'POSITIVE' or 'NEGATIVE'
- A confidence score: a probability between 0 and 1 indicating how confident the model is in its prediction

This approach offers classification-based sentiment analysis rather than a continuous sentiment spectrum.

Due to compatibility issues in JupyterLab, Hugging Face sentiment analysis was performed in Google Colab, which provided access to GPU acceleration—critical for processing large volumes of text efficiently.

Additionally, it was necessary to enable text truncation, as Hugging Face models (particularly RoBERTa-based ones) impose a token limit and would not process longer comments without truncation enabled.


### Areas of improvement:

Several processes in the project could have been further streamlined through function-based automation. Additionally, a more in-depth analysis of the 2020 and 2024 elections would have enriched the contextual understanding of the sentiment trends. A thorough evaluation of the strengths and limitations of each sentiment analysis tool could have improved sentiment classification accuracy and contributed to a more robust overall model. Expanding data collection to include more diverse sources would allow for a broader range of perspectives to be captured.

### Credit and Sources

**Technical Support:**
- Reddit
- Stack overflow
- Google Gemini
- ChatGPT

**Special Thanks:**
1. Hank Butler
2. Alanna Besaw

