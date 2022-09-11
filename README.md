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

