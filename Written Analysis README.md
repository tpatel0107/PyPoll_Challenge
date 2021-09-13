# Written Analysis of the Election Audit

**Overview of Election Audit: Purpose of the election audit is to 
	1) Provide the voter turnout for each county.
	2) Provide the percentage of votes from each county out of the total count. 
	3) Provide the county with the highest turnout. 

**Election-Audit Results
	*Total Votes cast were 369,711
	
	#code that yields above results

	# Initialize a total vote counter.
	total_votes = 0
	# Print the final vote count (to terminal)
    	election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")

    txt_file.write(election_results)
	
**Breakdown of number of number of votes and the percentage of total votes for each county in the precint
	        
		County Votes:
                Jefferson: 10.5% (38,855)

                Denver: 82.8% (306,055)

                Arapahoe: 6.7% (24,801)

	 #code that yields above results

          # 6a: Write a repetition statement to get the county from the county dictionary.
   		 for county_name in county_votes_:
       	  # 6b: Initialize a variable to hold the county’s votes as they are retrieved from the county votes dictionary.
        county_votes_all = county_votes_[county_name]
          # 6c: Calculate the percent of total votes for the county.
        county_voter_percentage = (float(county_votes_all) / float(total_votes)) * 100
          # 6d: Print the county results to the terminal.
        county_results = (f"{county_name}: {county_voter_percentage:.1f}% ({county_votes_all:,})\n")
        print(county_results)
          # 6e: Save the county votes to a text file.
        txt_file.write(county_results)
           
**The county with the largest number of votes was Denver
  	#code that yields above results

	 # 6f: Write a decision statement to determine the winning county and get its vote count.
        if (county_votes_all > turnout_count) and (county_voter_percentage > largest_turnout_per):
            turnout_count = county_votes_all
            largest_turnout_perc = county_voter_percentage
            largest__county_turnout = county_name
	 # 7: Print the county with the largest turnout to the terminal.
   	     winning_county_summary = (
             f"\n-------------------------\n"
             f"Largest County Turnout: {largest_county_turnout}\n"
             f"-------------------------\n")
             print(winning_county_summary, end="")

   	

**Breakdown of the number of votes and the percentage of total votes each candidate received
          
	     Largest County Turnout: 
             -------------------------
             Charles Casper Stockham: 23.0% (85,213)

             Diana DeGette: 73.8% (272,892)

             Raymon Anthony Doane: 3.1% (11,606)

	 # code that yields above results

	 # 8: Save the county with the largest turnout to a text file.
             txt_file.write(winning_county_summary)

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
         #  Save the candidate results to our text file.
         txt_file.write(candidate_results)

**Diana DeGette won the election, her vote count was 272,892 and winning percentage was 73.8%
         
	#code that yeilds above results
	
	#Determine winning vote count, winning percentage, and candidate.
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

    # Save the winning candidate's name to the text file
    txt_file.write(winning_candidate_summary)

**In summary election audit results provides an analysis of how votes were casted and where there was more voting due versus other counties where there was a low voting numbers. It also shows how some candidates faired much better than other candidates and in the end which candidate had the most votes based on final results. 
**Two ways this script can be formatted is 
	* We could add more counties so we could get more of an idea of the whole state. This would give us a bigger region, more data means we could get a better range of results. 
	* We could also add additional candidates so we could maybe have winners based on 1st, 2nd ,3rd and so onwards. This would provide us with a list of candidates that did better than others and break it down into sections.  