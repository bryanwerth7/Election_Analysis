# Election Analysis with Python
## Purpose of the Election Audit
I was given the task of auditing an election by the state election commission. They wanted to see the total votes cast, and the breakdown of each candidate's vote count and winning percentage. They also wanted to further investigate the election and break it down by county to see voter turnout on a more specific level. This analysis will not only reveal the winner, but give insight into which county had the largest turnout and percentage of votes for each candidate by county. 
## Election-Audit Results:
  - There were a total of 369,711 votes cast in the entire election.
  - As seen below, the county breakdown by highest number of votes was: Denver, Jefferson, and Arapahoe with 82.8%, 10.5%, and 6.7% respectively of the total votes. This was done using the code below with "xvotes" being the variable for each county:
```  
  for county_name in county_votes:
        votes = county_votes.get(county_name)
        xvotes_percentage = float(xvotes) / float(total_votes) * 100
```
  - The largest county voter turnout was Denver.
  - The total number of votes for the candidates can be seen below, ranking from most to least votes they are as follows: DeGette 73.8% (272,892), Stockham 23.0%  (85,213), and Doane 3.1% (11,606). This was done using a for loop inside of candidate_votes as seen below:
```
for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
```
  - The winning candidate was Diana DeGette with a vote count of 272,892, which was 73.8% of the total votes. Using an "if and" statement I determined the winning vote count, percentage, and candidate:
```
if (votes > winning_count) and (vote_percentage > winning_percentage):
        winning_count = votes
        winning_candidate = candidate_name
        winning_percentage = vote_percentage
```
<img width="512" alt="Screen Shot 2021-07-25 at 11 44 25 AM" src="https://user-images.githubusercontent.com/86524863/126905033-e4756f96-632d-425e-871a-ad653b56758c.png">

## Election Audit Summary
This python code could be used for any election with minor modifications, it could be scaled up statewide or even nationwide. The script can tally up each county votes and differentiate between any number of counties in any election. It could also be used to analyze data from within one city- analyzing voter turnout by maybe location inside the county, or any number of parameters like income, age, or party affiliation. This code could be modified to dive into one particular county to see why voter turnout is less than other counties- identifying a trend that could be used in the next election to try and boost voter turnout or help a candidate perform better in that county. 

**Politics depends on data to identify a myriad of useful information: which counties need more campaigning, which counties are producing the most turnout, which party different counties voted in prior elections etc. Using data is the KEY to getting the result you seek; the difference between winning and losing an election is in the data!**
