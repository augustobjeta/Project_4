# Social Media Sentiment vs. Polls: 
## Predicting U.S. Presidential Election Outcomes


**Problem Statement:**

**Can social media sentiment out perform or enhance traditional polling methodology?**

**We first needed to ask: How accurate is polling historically?**

    This project investigates whether traditional opinion polling or social media sentiment more accurately predicts U.S. presidential election winners. 

    Initial findings: Polling correctly predicts about 78% of elections across 1936–2024. Social media sentiment, however, captured certain “upset” years—such as 2016—where polls missed the mark.

**Motivation**

In the vast shadow of 21st century technological advancement, how are traditional methods for maintaining democracy tiding? 

Election forecasting directs campaign strategy and media coverage, to impact voter decision-making. Social media can provide a real time snapshot of public consciousness; Our goal: to capture it. 

**Should analysts and campaigns still trust polls, or does real-time sentiment offer a better signal?**

---
### Table of Contents

- Problem Statement 
- Data 

***Please note, data has since been consolidated into the data folder. Please adjust filepaths in ```pd.read_csv``` in the notebooks to correct the file paths to access csv's.***

- Historical Polling
- Campaign Social Media:
  - To be used in conjunction with youtube_playlist_scraper.ipynb
  - 2016
  - 2020
  - 2024
- Data dictionary
- Preprocessing
- Challenges
Methodology
- Vader
- HuggingFace
Results
- key findings
- Tables and Figures
- Model Performance
- Conclusion
Setup and Usage
Contributors
Additional Information

*** Notebooks: ***

___

## Data Sources

**Historical Polling:**
- [Wikipedia: Polling for United States presidential elections](https://en.wikipedia.org/wiki/Polling_for_United_States_presidential_elections) (CSV)
- [270toWin: Historical Presidential Elections](https://www.270towin.com/historical-presidential-elections/) (CSV)

### Social Media Scraping: YouTube 

- There were over 680,000 comments scraped from 70 videos.
- Usable observations differed greatly.
- For example the 2016 data after cleaning, there were 30,269 total observations for the democratic dataframe, and there were only 1,614 total observations for the republican dataframe.
- Observations often fell to blow 50 percent of the originally collected observations.

#### 2016 Campaign speechs:

Hillary playlist: PL3-OIwNPoC3Lj68487lgoJiwrXx5lVO8e
Comments stored: Data/2016hillary_comments.csv

June 7, 2016, Hillary Clinton makes history (Full speech)
https://www.youtube.com/watch?v=FN6KBbug9gA

July 25, 2016, Hillary Clinton's full speech at the 2016 Democratic National Convention:
https://www.youtube.com/watch?=C6GnHBEBWYE

August 8, 2016, Hillary Clinton Kissimmee FULL Speech 8/8/16
https://www.youtube.com/watch?v=HG6MEdn1QBs

September 23, 2016, Mirrors | Hillary Clinton
https://www.youtube.com/watch?v=vHGPbl-werw

October 31, 2016, Hillary Clinton FULL SPEECH | Kent, Ohio Rally:
https://www.youtube.com/watch?v=_uqmcnwjHrY

November 8, 2016, Full Video: Hillary Clinton holds a midnight rally in North Carolina on election eve
https://www.youtube.com/watch?v=n7Tamj06FQs

Comment total with replies: 1669
Comment total without replies: 1001

Trump playlist: PL3-OIwNPoC3II9mG8jLIN8ODWydLnU1bB
Comments stored: 'Data/2016trump_comments.csv'

June (May 25th, 2016), Donald Trump Rally in Anaheim, CA
https://www.youtube.com/watch?v=ltNVyvK8Paw

Jul 21, 2016, FULL SPEECH: Donald Trump at RNC. Republican National Convention. Cleveland, Ohio. 
https://www.youtube.com/watch?v=F5XmFG3221s

August 19, 2016, Watch Donald Trump's First Campaign TV Ad
https://www.youtube.com/watch?v=FEgykfioeuw

September 6, 2016 Full Speech: Donald Trump Rally in Greenville, NC 
https://www.youtube.com/watch?v=gXMAvppTSAY

October 30, 2016 Full Speech: Donald Trump Rally in Greeley, CO
https://www.youtube.com/watch?v=aMZsKq99hdk

November 5, 2016 Full Speech: Donald Trump Rally in Denver, CO
https://www.youtube.com/watch?v=KIKNSZ_Nf3w

Comment total with replies: 4721
Comment total without replies: 2023

### 2016 Debates -
There were 3 presidential debates in 2016: September 26, 2016, October 9, 2016, October 19, 2016. We aimed for an equal distribution of videos from each political "type" of media sources. The types are "Right" and "Left." An important note a [Pew research article](https://www.pewresearch.org/journalism/2014/10/21/section-1-media-sources-distinct-favorites-emerge-on-the-left-and-right/) showed a great spread in trust of sources left of the center in regards to American politics. For this reason we have a range from "middle" to mid-left news sources in an attempt to represent "the most" Americans perspectives. 


#### Dem media:
Playlist: https://www.youtube.com/watch?v=rfq0Yw2sMq0&list=PL3-OIwNPoC3Lhs0Iob2u9_jMaBhubek3r
Comments stored: 'Data/2016Dem_debate_comments.csv'

September 26:
[The First Presidential Debate: Hillary Clinton And Donald Trump (Full Debate) | NBC News](https://www.youtube.com/watch?v=855Am6ovK7s) 40098

October 9: 
[Second Presidential Debate | Election 2016 | The New York Times](https://www.youtube.com/watch?v=rfq0Yw2sMq0) 6966

[The Second Presidential Debate: Hillary Clinton And Donald Trump (Full Debate) | NBC News](https://www.youtube.com/watch?v=FRlI2SQ0Ueg) 40199

23ABC [FULL VIDEO: Donald Trump vs Hillary Clinton - 2nd Presidential Debate](https://www.youtube.com/watch?v=h-gkBUbU_F4)1861

October 19: 
[CBS News - Full 2016 Final Presidential Debate](https://www.youtube.com/watch?v=FZ_G5j9yVIU) 931
[LIVE: Third Presidential Debate (C-SPAN)](https://www.youtube.com/watch?v=ANT_ZBhpvtw&t=173s) 2531
[Final 2016 Presidential Debate (Full) | The New York Times](https://www.youtube.com/watch?v=Z_pEb1bDN-w)   1666

Comment total with replies: 94219
Comment total without replies: 52283

#### Rep media:
Playlist: https://www.youtube.com/watch?v=lTgieGfYVQs&list=PL3-OIwNPoC3JFEvZP_nSMPrib8viH2KX-
Comments stored: ''Data/2016Rep_Debates_comments.csv'

September 26: 
[Highlights from the first presidential debate](https://www.youtube.com/watch?v=lTgieGfYVQs) 69
FOX[FULL DEBATE: Donald Trump And Hillary Clinton First Presidential Debate (FNN)](https://www.youtube.com/watch?v=lIexQNGxwog) 388

October 9:

October 19: Saved in 3 parts
Fox News
[Part 1 of third presidential debate at University of Nevada](https://www.youtube.com/watch?v=cyx5e2c1SgU)
347
[Part 2 of third presidential debate at University of Nevada
](https://www.youtube.com/watch?v=BgPENwntzKk)152

[Part 3 of the Fox News GOP presidential debate in Detroit](https://www.youtube.com/watch?v=Uaujjp3JKGY)458

[cbc news 
CBC News Special: Final Trump-Clinton presidential debate](https://www.youtube.com/watch?v=dXWdiz--X0s) 425

[NBC News-YouTube Democratic Debate (Full)](https://www.youtube.com/watch?v=ti2Nokoq1J4)9166


Comment total with replies: 11005
Comment total without replies: 5569


### 2020 Videos scraped for comments - 

#### Campaign speechs:
Biden playlist: PL3-OIwNPoC3IHwPNuYmzxr6Lk7Fx_XViX
Comments stored: Data/2020biden_comments.csv

April 29 : Bloomberg News
[Joe Biden Kicks Off Campaign With First Rally in Pittsburgh](https://www.youtube.com/watch?v=lFISnAndKOA) 365

April 29 : CBS [Joe Biden kicks off campaign with first rally in Pittsburgh](https://www.youtube.com/watch?v=ApsEgQvHfIo)780

May 18 : Joe Biden Campaign [Joe Biden Officially Launches Campaign for President](https://www.youtube.com/watch?v=FaN-Pf_LW1Q) 485

June 11 : Washington Post [Biden campaigns in Iowa](https://www.youtube.com/watch?v=pB4BxNjMb7Q)320

July 6 : MSNBC [Joe Biden Speaks in Sumter, South Carolina | Joe Biden for President](https://www.youtube.com/watch?v=DvWrekxwo2o)128

August 7 : Joe Biden Campaign [Joe Biden: We're in a Battle for the Soul of our Nation](https://www.youtube.com/watch?v=FiPVOx-cAfQ)389

September 2 : DMRegister [Full speech: Joe Biden speaks at Labor Day picnic in Iowa City, Iowa](https://www.youtube.com/watch?v=9GvZh9Rs7nE) 38

October 31 : NBC [Biden And Obama Campaign In Michigan | NBC News](https://www.youtube.com/watch?v=Tc0Gb6coKKQ)5678

November 2 : [Joe Biden holds drive-in campaign rally in Pittsburgh, Pennsylvania](https://www.youtube.com/watch?v=Fkh0DXiCvPA)485


Comment total without replies: 4357 

Trump playlist: PL3-OIwNPoC3LAML6nXUF4D1ynbi17-ILC 
Comments stored: 'Data/2020trump_comments.csv'

May 20, 2020: Fox News [FULL RALLY: President Trump in Montoursville, Pennsylvania](https://www.youtube.com/watch?v=GgINUxecNrg) 1280

June 20, 2020: Yahoo Finance [President Trump holds rally in Tulsa, Oklahoma, amid coronavirus spread concerns](https://www.youtube.com/watch?v=niCxnEyG0SM)5401

July 4, 2020:USA Today [President Trump's full speech at Mount Rushmore | USA TODAY](https://www.youtube.com/watch?v=mXD4zPY4Ai0&t=56s) 15386

August 15, 2019: CBS [Trump in New Hampshire for 2020 campaign rally](https://www.youtube.com/watch?v=Iw_lKnYHrDc) 361

September 12, 2020: One America News Network [President Trump Holds Campaign Rally in Minden Nevada 9/12/20](https://www.youtube.com/watch?v=5nD2s9dWess) 1547

October 21, 2020: NBC [Trump Speaks At Campaign Rally In Pennsylvania | NBC News](https://www.youtube.com/watch?v=wolUfDLP2Kw)434

November 1, 2020 [Trump Holds Campaign Rally In Michigan | NBC News](https://www.youtube.com/watch?v=BRnyOdnDpmc) 1077 


Comment total without replies: 10398

### 2020 Debates -
There were 2 presidential debates in 2020: September 29 and October 22. We aimed for an equal distribution of videos from each political "type" of media sources. The types are "Right" and "Left." An important note a [Pew research article](https://www.pewresearch.org/journalism/2014/10/21/section-1-media-sources-distinct-favorites-emerge-on-the-left-and-right/) showed a great spread in trust of sources left of the center in regards to American politics. For this reason we have a range from "middle" to mid-left news sources in an attempt to represent "the most" Americans perspectives. 

For comments collected we did not include comment replies or repeated commmentators.
Comments were limited to those posted prior to the election results.

#### Dem Media:
Playlist: PL3-OIwNPoC3Lpa7NKQXfKolxzEjel7x6A
Comments stored: 'Data/2020Dem_debate_comments.csv'

September 29, 2020: CNN [Replay: The first 2020 presidential debate on CNN](https://www.youtube.com/watch?v=yHFI8TsSKXY)29233

September 29, 2020: CBS [Trump and Biden face off in chaotic first 2020 presidential debate | FULL DEBATE](https://www.youtube.com/watch?v=9HnKFUNlcfY)11622

October 22, 2020: CNN [Replay: The final 2020 presidential debate on CNN](https://www.youtube.com/watch?v=rOn7uGVVf1I)9298

October 22, 2020: NBC [Final 2020 Presidential Debate Between Donald Trump, Joe Biden | NBC News](https://www.youtube.com/watch?v=UCA1A5GqCdQ)14,293

Comment total without replies: 25944

#### Rep Media:
Playlist: PL3-OIwNPoC3I8nu1EMXZbL9YFuqb1XAkj
Comments stored: ''Data/2020Rep_Debates_comments.csv'

September 29, 2020: Sky News [Watch In Full: Trump versus Biden in the first US Presidential election debate](https://www.youtube.com/watch?v=K8Z9Kqhrh5c&t=516s)18805

September 29, 2020: CSPAN [First 2020 Presidential Debate between Donald Trump and Joe Biden](https://www.youtube.com/watch?v=wW1lY5jFNcQ)110398

October 22, 2020: WSJ [Full Debate: President Trump and Joe Biden Square Off for Final Time Ahead of Election | WSJ](https://www.youtube.com/watch?v=RHISJrOODJ4)6455

October 22, 2020: CSPAN [Second 2020 Presidential Debate between Donald Trump and Joe Biden](https://www.youtube.com/watch?v=bPiofmZGb8o)113,855

Comment total without replies: 17235

### 2024 Media - 

NOTE: Kamela announced her candidacy July 2024. This changed the window of our data collection to July - November 2024 as oppsed to April-Novemeber of the campaign election year.

#### Campaign speechs:
Kamela playlist: PL3-OIwNPoC3ITusqZ8RCe9ssy0ApktiBk
Comments stored: Data/2024kamela_comments.csv

July 21, 2024: ABC News[Biden endorses Kamala Harris for 2024 presidential election](http://youtube.com/watch?v=V_I7gRpwTBc)886

July 30, 2024: Fox(local) [FULL: Kamala Harris speech at Atlanta rally | FOX 5 News](https://www.youtube.com/watch?v=_lpYc-Ww8j4)11545

August 11, 2024: WFAA, ABC [FULL SPEECH: Kamala Harris holds rally in Las Vegas (August 11, 2024)](https://www.youtube.com/watch?v=3P_lKUqz9E8) 1404

August 6,2024: Fox(local) [Kamala Harris, Tim Walz Philadelphia Rally: FULL SPEECHES](https://www.youtube.com/watch?v=rONg2cCqFBk) 1221

September 25, 2024: WFAA, ABC [Kamala Harris full speech Pittsburgh, PA (Sept. 25, 2024)](https://www.youtube.com/watch?v=-i64tqglpmA)1443

October 4, 2024: Kamala Harris Campaign [Rally in Flint, MI for VP Kamala Harris | Harris-Walz 2024](https://www.youtube.com/watch?v=gVzjoxj-ZQQ)2107

November 4, 2024: WFAA, ABC [Kamala Harris full speech at campaign rally in Pennsylvania](https://www.youtube.com/watch?v=TlR70XK8LiA)474

Comment total without replies: 10200

Trump2024 playlist: PL3-OIwNPoC3LxBJ6G_jJYpX98W0AoGYoY
Comments stored: 'Data/2024trump_comments.csv'

July 19, 2024Fox [WATCH: Former President Trump FULL SPEECH at the 2024 RNC | LiveNOW FOX](https://www.youtube.com/watch?v=YEsd7esFjbw) 5299

August 21, 2024: Fox 4 [Donald Trump NC Rally: FULL SPEECH](https://www.youtube.com/watch?v=aKN7R92eoxM) 428

September 21, 2024: FOX 4 [LIVE: Donald Trump Rally in NC | FOX 4](https://www.youtube.com/watch?v=OZXpNddHBm8)934

September 21, 2024: WFAA ABC [Donald Trump full speech at campaign rally in Wilmington, NC (Sept. 21, 2024)](https://www.youtube.com/watch?v=xC9rEV0GQ2c&list=PL3-OIwNPoC3LxBJ6G_jJYpX98W0AoGYoY&index=3)279 

October 24, 2024: WFAA ABC [Donald Trump full speech at Latrobe, PA rally (Oct. 19, 2024)](https://www.youtube.com/watch?v=bI_lAV16738) 614

November 1, 2024: FOX [WATCH: Trump FULL SPEECH in Michigan, first rally since assassination attempt | LiveNOW FOX](https://www.youtube.com/watch?v=4v46FwsLUOc) 5722

Comment total witout replies: 7844

### 2024 Debate videos -
There was 1 presidential debate between Kamela and Trump on September 10, 2024. Playlists contain streams. hosted by a range of media agencies to ensure a range in viewer base. We aimed for an equal distribution of videos from each political "type" of media sources. The types are "Right" and "Left." An important note a [Pew research article](https://www.pewresearch.org/journalism/2014/10/21/section-1-media-sources-distinct-favorites-emerge-on-the-left-and-right/) showed a great spread in trust of sources left of the center in regards to American politics. For this reason we have a range from "middle" to mid-left news sources in an attempt to represent "the most" Americans perspectives. 

All videos of Debate on September 10, 2024
The imbalance in number of videos is based on comments per video, that is what was being considered.

#### DEM media:
Playlist: PL3-OIwNPoC3L405ZyoH5Yb6oR_Od49j7i
Comments stored: 'Data/2024Dem_debate_comments.csv'

ABC [Presidential debate highlights from Trump and Harris's first showdown of 2024](https://www.youtube.com/watch?v=4aw5FziSc14) 6334

MINT [US Presidential Debate 2024: Top Highlights | Kamala Harris Vs Donald Trump | Best 9 Minutes](https://www.youtube.com/watch?v=npgogT5ir4M) 11560

BLOOMBERG NEWS [Trump-Harris Presidential Debate Highlights](https://www.youtube.com/watch?v=WATb4fet7MA)749

Boston Globe [Highlights from the Trump-Harris presidential debate](https://www.youtube.com/watch?v=OQgE0ETV81s) 15365

PBS [The Choice 2024: Harris vs. Trump (full documentary) | FRONTLINE](https://www.youtube.com/watch?v=yjPxL5w3OOU)15727

NBC[Watch closing statements from Harris and Trump at 2024 presidential debate](https://www.youtube.com/watch?v=fpu1QEB03xA) 885

ABC [DEBATE REPLAY: VP Harris and former President Trump l ABC News Presidential Debate](https://www.youtube.com/watch?v=4dOgWZsDB6Q)20013

CNN [Must-watch moments and analysis of Trump and Harris’s first presidential debate](https://www.youtube.com/watch?v=kADujQsWO68) 5773

Comment total without replies: 36480

#### REP media:
Playlist: PL3-OIwNPoC3KQ4d8hMwGIQnBB4A3Dm3UO
Comments stored: 'Data/2024Rep_debate_comments.csv'

WSJ[Full Debate: Harris vs. Trump in 2024 ABC News Presidential Debate | WSJ](https://www.youtube.com/watch?v=VgsC_aBquUE)85572

FOX [Trump, Harris face off at the ABC News Presidential Debate](https://www.youtube.com/watch?v=4IGd0BrrXoI) 15060

Comment total witout replies: 51652

**Data Dictionary:**  
See [Baseline_Model_Data.csv](Baseline_Model_Data.csv) and [YouTube dataset](youtube_scraper.ipynb) for column definitions:
- `year`: Election year
- `Poll_Leader`: Party leading in polls (Democrat/Republican)
- `Poll_Leading_Margin`: Poll lead size (percentage points)
- `EC_election_winner`: Electoral College winner (Democrat/Republican)
- `sentiment_score`: Compound VADER sentiment (YouTube data)
- (etc. — see data files for all variables)

**Data Preprocessing Steps:**
- **Polling data:** Scraped, averaged monthly polling for each party/year, engineered features for leader/margin, matched with election results.
- **YouTube sentiment:** Scraped comments for selected events, deduplicated, removed replies, and labeled by candidate/event for fairness and reproducibility.

#### Data Collection Challenges

Our initial plan was to scrape data from Twitter and Reddit. However, several limitations led us to reconsider:

**Twitter:**
    - Access to the Twitter API has become prohibitively expensive, making large-scale data collection unfeasible for this project.

**Reddit:**
- The two main Reddit APIs have significant constraints:
  - PRAW (Python Reddit API Wrapper) is still functional but only supports scraping from the top, hot, and new posts. It does not allow filtering by custom timeframes and has a hard limit of 1,000 posts per query.
  - Pushshift, which previously allowed time-based filtering and more flexible querying, has been offline since 2023, making it unavailable for use.

**Final Approach – YouTube:**
- Due to these limitations, we shifted our focus to YouTube comments, which offered an accessible and rich source of user-generated content. This allowed us to collect timely political discourse data with fewer restrictions on volume or timeframe.

### ***Data Cleaning and Processing Observations***

Deduplication:** Retained only one comment per user to reduce repetition and bias in sentiment distribution. Many users also reposted the same or similar comments, leading to a high volume of duplicates that require removal or consolidation. 

Thread Misuse: Replies are often posted as new top-level comments rather than nested replies, disrupting the natural conversational flow.


---

## Methodology

### Approach

- **Polling:** Logistic regression (main), random forest for robustness.
  
### **Sentiment:** VADER and Hugging Face sentiment models on YouTube comments, compared to actual election outcomes.
#### Primary Sensitivity Analysis Tool:
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


### Alternative Model - HuggingFace

**Hugging Face Sentiment Analysis:**
Unlike VADER, which produces a numerical compound sentiment score ranging from -1 to 1, Hugging Face’s sentiment-analysis pipeline provides:
- A sentiment label: 'POSITIVE' or 'NEGATIVE'
- A confidence score: a probability between 0 and 1 indicating how confident the model is in its prediction

This approach offers classification-based sentiment analysis rather than a continuous sentiment spectrum.

Due to compatibility issues in JupyterLab, Hugging Face sentiment analysis was performed in Google Colab, which provided access to GPU acceleration—critical for processing large volumes of text efficiently.

Additionally, it was necessary to enable text truncation, as Hugging Face models (particularly RoBERTa-based ones) impose a token limit and would not process longer comments without truncation enabled.


### Software and Libraries

- **Python 3.8+**
- `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
- `beautifulsoup4` (scraping), `nltk` (VADER), `transformers` (Hugging Face)
- Jupyter Notebook
- Google Colab Notebook

### Key Steps

- Data scraping and cleaning
- Exploratory data analysis (EDA)
- Feature engineering (poll leader, margin, sentiment scores)
- Model training and evaluation:
    - **Polling:** Logistic regression, accuracy, confusion matrix, LOOCV
    - **Sentiment:** VADER sentiment scoring, Hugging Face model outputs, accuracy against actual results
- Comparison of polling vs. sentiment models

---

## Results

### Key Findings

- **Polling:** Logistic regression using polling leader/margin predicts about **78%** of winners (using LOOCV), with most errors during “upset” years.
- **Sentiment:** VADER-based sentiment analysis explained certain surprising outcomes, most notably 2016, where YouTube sentiment captured a Republican surge polls missed.
- **Comparison:** In recent cycles, social sentiment sometimes matched or exceeded the predictive power of polls.

### Tables and Figures

- Accuracy by year (bar/line charts): Visual comparisons of polling model accuracy across all presidential election cycles, and bar graphs showing years when polls or sentiment accurately predicted the winner.
- Confusion matrices for model outputs: For both polling and sentiment models, confusion matrices show where each model got results right or wrong by party and year.
- Year-by-year upset visualizations: Charts highlight which cycles had “upset” outcomes, where sentiment diverged from polls and the actual result.
- **Sentiment analysis visualizations:** Figures showing the distribution of sentiment scores by candidate, cycle, and party. These visuals helped trace how online mood correlated with real election results.
- **Hugging Face model outputs:** Additional figures demonstrate how deep learning-based sentiment labels compared to VADER sentiment, offering another perspective on “positive” vs “negative” election sentiment.

### Model Performance

- Polling model accuracy: **78%** (LOOCV)
- Sentiment model accuracy: VADER sentiment analysis successfully matched the real winner in the 2016, 2020, and 2024 cycles, including correctly “calling” the 2016 Republican win that polling missed. Hugging Face-based sentiment labels tracked closely with VADER and actual election results, reinforcing the predictive value of social sentiment.
- See notebook visuals for precision, recall, and historical trend graphs
- **Key takeaways:** Sentiment models were particularly valuable in cycles with major polling upsets, capturing shifts in public mood and “hidden” support not measured by traditional surveys.
  

---

## Conclusion

**Summary of Findings:**  
- Polling is still a valuable tool but has clear blind spots—especially when public mood shifts fast, or hidden voters are missed.
- Sentiment analysis can capture shifts missed by polls, but is limited by data quality, comment restrictions, and retrospective analysis.

**Limitations:**  
- YouTube comments are not a representative sample of all voters.
- Some official campaign channels restrict or delete comments.
- Both polling and sentiment data are subject to bias and historical change.

**Future Work:**  
- Standardize project reqirments, for example: number of usable comments per candidate.
- Experiment with real-time sentiment tracking and more advanced models.
- Analyze state-level or demographic breakdowns.
  

---

## Setup and Usage

**Installation Instructions:**
- Clone this repository
- Install requirements with `pip install -r requirements.txt` (if available)

**Running the Code:**
- Open and run `Baseline_Model_Data.ipynb` (polling analysis)
- Open and run `youtube_scraper.ipynb` (data collection) and `processing_modeling_visualization.ipynb` (sentiment analysis)

**Example Usage:**
- See provided notebooks for usage examples and to reproduce all results
  

---

## Contributors

- **August** – Strategy, Structure, Data Sourcing, Youtube Data Scraping
- **Swathi** – Polling Data Scraping, Baseline Modeling
- **Waleed** – Sentiment Analysis Modeling
  
### Credit and Sources

**Technical Support:**

- Reddit
- Stack overflow
- Google Gemini
- ChatGPT
- Jupyter Labs
- Colab
- Python
  
 **Special Thanks:**
1. Hank Butler
2. Alanna Besaw

 
---

## Additional Information

Please reachout to: augustvollbrecht@gmail.com with any questios or sugestions!

**Licensing:** MIT License 


**Reproducibility:**  
- All data sources and code are included or linked.
- Notebooks are executable from top to bottom with the provided datasets.
- Results can be reproduced by running the notebooks as described above.
