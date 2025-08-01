OUTLINE TO BE REPLACES WITH OUR TEXT:
.....

****WIll need to tell user how to obtain api key since we cannot store one for them... instructions here:
http://youtube.com/watch?v=SIm2W9TtzR0

video for scraping here: https://github.com/analyticswithadam/Python/blob/main/YouTube_Comments_Advanced.ipynb

How to scrape youtube playlists:
video - https://www.youtube.com/watch?v=A1III_DQU4I
code -https://github.com/analyticswithadam/Python/blob/main/Pull_all_Comments_and_Replies_for_YouTube_Playlists.ipynb


Project name: Social Media Sentiment Analysis vers Polls, contact email 
augustvollbrecht@gmail.com, available to External users (only option offered)


OUTLINE OF NOTEBOOKS?PROJECT FOLDER CONTENTS - state to be outlined in same order in README


You will have to acquire your own YouTube v3 api to access data.

________________________


## Sentiment Data Collections
We focused on the middle of the road platforms to collect our data. WE ideally would have included reddit commentary but it is no longer publicly available. Youtube is a great substitute as it appeals to an extremely broad range of users.


Next media was selected. Criteria was based on reproducibility. Media was selected on the premise that it would likely be produced and published similarly in future debates. The criteria made it obvious to choose media fundamental to and highly anticipated in every presidential campaign: rally speeches and debates.


The data had to be parsed differently as the comments on each candidate's videos could easily be classified as for or against/positive or negative, whereas for debate videos comments could be in support of either candidate.

Our solution to the increased categories of responses that could be encountered on the debate videos was to sample equally from Democratic leaning and Republican leaning videos. We kept the comments separate and from Dem videos we classified the data as either for or against HC and debates that aired on Republican media outlets were classified as either for or against DT.


MAKE A DATA DICTIONARY FOR YOUR CSV'S!

### 2016 Videos scraped for comments - 

#### Campaign speech videos:
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

### DEBATE videos -
There were 3 presidential debates in 2016: September 26, 2016, October 9, 2016, October 19, 2016. We aimed for an equal distribution of videos from each political "type" of media sources. The types are "Right" and "Left." An important note a [Pew research article](https://www.pewresearch.org/journalism/2014/10/21/section-1-media-sources-distinct-favorites-emerge-on-the-left-and-right/) showed a great spread in trust of sources left of the center in regards to American politics. For this reason we have a range from "middle" to mid-left news sources in an attempt to represent "the most" Americans perspectives. 


#### NBC/NTY/NBC/ABC/CBS/CSpan:
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

#### FOX/CBC/NBC/Newsmax/NewYorkPost:
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

#### Campaign speech videos:
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

### DEBATE videos -
There were 2 presidential debates in 2020: September 29 and October 22. We aimed for an equal distribution of videos from each political "type" of media sources. The types are "Right" and "Left." An important note a [Pew research article](https://www.pewresearch.org/journalism/2014/10/21/section-1-media-sources-distinct-favorites-emerge-on-the-left-and-right/) showed a great spread in trust of sources left of the center in regards to American politics. For this reason we have a range from "middle" to mid-left news sources in an attempt to represent "the most" Americans perspectives. 

For comments collected we did not include comment replies or repeated commmentators.
Comments were limited to those posted prior to the election results.

#### NBC/NTY/NBC/ABC/CBS/CSpan:
Playlist: PL3-OIwNPoC3Lpa7NKQXfKolxzEjel7x6A
Comments stored: 'Data/2020Dem_debate_comments.csv'

September 29, 2020: CNN [Replay: The first 2020 presidential debate on CNN](https://www.youtube.com/watch?v=yHFI8TsSKXY)29233

September 29, 2020: CBS [Trump and Biden face off in chaotic first 2020 presidential debate | FULL DEBATE](https://www.youtube.com/watch?v=9HnKFUNlcfY)11622

October 22, 2020: CNN [Replay: The final 2020 presidential debate on CNN](https://www.youtube.com/watch?v=rOn7uGVVf1I)9298

October 22, 2020: NBC [Final 2020 Presidential Debate Between Donald Trump, Joe Biden | NBC News](https://www.youtube.com/watch?v=UCA1A5GqCdQ)14,293

Comment total without replies: 25944

#### FOX/CBC/CSPAN/NBC/Newsmax/NewYorkPost:
Playlist: PL3-OIwNPoC3I8nu1EMXZbL9YFuqb1XAkj
Comments stored: ''Data/2020Rep_Debates_comments.csv'

September 29, 2020: Sky News [Watch In Full: Trump versus Biden in the first US Presidential election debate](https://www.youtube.com/watch?v=K8Z9Kqhrh5c&t=516s)18805

September 29, 2020: CSPAN [First 2020 Presidential Debate between Donald Trump and Joe Biden](https://www.youtube.com/watch?v=wW1lY5jFNcQ)110398

October 22, 2020: WSJ [Full Debate: President Trump and Joe Biden Square Off for Final Time Ahead of Election | WSJ](https://www.youtube.com/watch?v=RHISJrOODJ4)6455

October 22, 2020: CSPAN [Second 2020 Presidential Debate between Donald Trump and Joe Biden](https://www.youtube.com/watch?v=bPiofmZGb8o)113,855

Comment total without replies: 17235



### 2024 Videos scraped for comments - 

NOTE: Kamela announced her candidacy July 2024. This changed the window of our data collection to July - November 2024 as oppsed to April-Novemeber of the campaign election year.

#### Campaign speech videos:
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

### DEBATE videos -
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

________________________
1. Project Title & Overview:
Concise and Descriptive Title: A title that clearly conveys the project's purpose and scope. 
Brief Project Description: A short paragraph summarizing the project's goals and key findings. 
Motivation: Explain why this project is important and what problem it addresses. 
Visuals (Optional): Consider adding a relevant banner or image to capture attention. 
2. Data Sources:
List and Describe Data:
.
Clearly list all datasets used, including their sources, formats (e.g., CSV, JSON), and any relevant links.
Data Dictionary:
.
Include a data dictionary or link to one that describes the variables, their meaning, and possible values.
Data Preprocessing Steps:
.
Briefly outline any data cleaning, transformation, or feature engineering steps taken. 
3. Methodology:
Approach: Describe the chosen data science techniques, algorithms, or models. 
Software and Libraries: Specify the programming languages (e.g., Python, R) and libraries used. 
Key Steps: Outline the main steps of the analysis, including data exploration, model training, and evaluation. 
4. Results:
Key Findings:
Summarize the most important results of the analysis, using visualizations or statistics as appropriate.
Tables and Figures:
Include tables and figures to present the results in a clear and concise manner.
Model Performance:
Report on model evaluation metrics, such as accuracy, precision, recall, etc. 
5. Conclusion:
Summary of Findings: Briefly reiterate the main findings and their implications. 
Limitations: Acknowledge any limitations of the study, such as data biases or model shortcomings. 
Future Work: Suggest potential directions for future research or improvements. 
6. Setup and Usage:
Installation Instructions: Provide clear instructions on how to install the necessary software, libraries, and dependencies.
Running the Code: Explain how to execute the code, including any necessary arguments or parameters.
Example Usage: Provide a simple example of how to use the code or access the results. 
7. Contact Information:
Principal Investigator: Name and contact information of the person responsible for the project.
Data Manager: If applicable, include the contact information for the data manager. 
8. Additional Information:
Licensing: Specify the license under which the project is released. 
Version Control: If applicable, include information about version control and how to access previous versions. 
Reproducibility: Highlight any steps taken to ensure the reproducibility of the results. 
Code of Conduct: If relevant, include a code of conduct for the project. 