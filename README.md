# Election Analysis – Using Python
## Overview
I have been asked by Tom, a Colorado board of election employee to assist him in an election audit of the tabulated results for a U.S. congressional precinct in Colorado. The key objectives for reporting were
•	The total number of votes cast.
•	Complete list of candidates who received votes
•	Total number of votes for each candidate 
•	Percentage of votes each candidate
•	Winner of the election based on popular vote.

The board wanted us to automate the process using Python. If the audit results were up to expectation of the board, there was a chance that our method and findings would be extended to other congressional districts and senatorial districts and local elections.


Based on our initial findings, the board asked to report some additional information objectives

•	Voter Turnout for each County.
•	Percentage of votes contributed by each county to the election.
•	Largest County in terms of voter turnout.

## Election Outcomes

Based on our analysis, we were able to provide the best possible answers to the objectives set by the board
1.	The total number of votes cast in the election were 369,711.

```

# Save the results to our text file.
with open(file_to_save, "w") as txt_file:

    # Print the final vote count (to terminal)
    election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")
```

2. Breakdown of votes won by each county and percentage total for each county in Colorado
    a.	Jefferson – 38,855 (10.5%)
    b.	Denver – 306,055 (82.8%)
    c.	Arapahoe – 24,801 (6.7%)
    
   ``` 

	# 6a: Write a for loop to get the county from the county dictionary.
	    for county_name in county_votes:
	
	        # 6b: Retrieve the county vote count.
	        county = county_votes.get(county_name)
	        # 6c: Calculate the percentage of votes for the county.
	        county_percentage = float(county) / float(total_votes) * 100
	
             # 6d: Print the county results to the terminal.
	        county_results = (
	            f"{county_name}: {county_percentage: .1f}% ({county:,})\n")
	        
	        print(county_results, end="")

  ```
  
 3.  Denver had the largest voter turnout (winning counting vote: 306,855 votes) and received 82.8% of the total votes in Colorado.
   
   
   ```
    # 6f: Write an if statement to determine the winning county and get its vote count.
        if (county > winning_county) and (county_percentage > winning_c_percentage):
            winning_county = county
            winning_c_candidate = county_name
            winning_c_percentage = county_percentage

    # 7: Print the county with the largest turnout to the terminal.
    winning_county_summary = (
        f"-------------------------\n"
        f"Largest County Turnout: {winning_c_candidate}\n"
        f"Winning County Vote: {winning_county:,}\n"
        f"Winning County Percentage: {winning_c_percentage:.1f}%\n"
        f"-------------------------\n")  
    print(winning_county_summary)

    ```
    
  4.  Breakdown of votes won by each candidate and percentage of the total votes polled in Colorado.
        a.	Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
        b.	Diana DeGette received 73.8% of the vote and 272,892 number of votes.
        c.	Raymon Anthony Doane received 3.1% of the vote and 11,606 number of votes.
	
    ```
    
    
    # Save the final candidate vote count to the text file.
	    for candidate_name in candidate_votes:
	
	        # Retrieve vote count and percentage
	        votes = candidate_votes.get(candidate_name)
	        vote_percentage = float(votes) / float(total_votes) * 100
	        candidate_results = (
	            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")	
	        # Print each candidate's voter count and percentage to the
	        # terminal.
	        print(candidate_results)
            # Save the candidate results to our text file.
	        txt_file.write(candidate_results)

     ```    
     
  5.  The winner of the election was Diana DeGette with 272,892   votes and got 73.8% of the total votes cast in the 3 counties of Colorado.
     
     ```
     
     # Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

    # Print the winning candidate (to terminal)
    winning_candidate_summary = (
        f"-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
     print(winning_candidate_summary)
     
     ```
     
  ## Summary – business proposal to Election commission
  
We used Python programming to analyze the election results file by iterating through each row and reading the data in the second and third columns, 'County' and 'Candidate' to calculate and print the results. This code is a very general and helpful script used as a template for future elections such as local, senatorial, and presidential elections.

In the case of a senatorial election, we will have to analyze data at a district and state level. The program would have to run through additional columns of information regarding different districts and states. We need to define a nested loop with a decision statement to go through each county in a state before moving to the next state. 

We can analyze the voter-level data for demographics (age, sex, race, religion), party allegiance (democrats/ republicans), and voting type (ballot, mail, voting machine). We can easily add these as new columns to the dataset and apply the same decision and repetition statements used for counting and assigning the total winning votes per candidate and county.



   
