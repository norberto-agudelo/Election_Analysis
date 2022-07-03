# Module 3. Election Analysis
## Overview of Election Audit

The main purpose of this job is to generate a report that shows the Colorado Congressional elections results where three candidates were running on three counties. 

This audit analysis includes not only the winner of the elections but the total number of votes cast, the total numbers of votes for each candidate at each county as well the percentage of votes for each candidate.

The ultimate goal is to certify the result of the race at that state. Although this aim, to know who is the winner of the election is the most important result on this audit analysis, this information is also extremely useful for candidates, politics, government and others in order to know how voters cast their votes, how votes are distributed on each county and eventually how parties must approach to future elections.

Based on a .csv file that contains three columns (Ballot Id, County and the candidate’s name) Tom who is a Colorado Board of Elections must use Python as software tool to write code that created the report stated above

## Election-Audit Results

o	As the report shows as the terminal line as well as the .txt file, the total number of votes cast in that congressional election was 369,711. This value is the number of rows in the file minus the one with header and it is the result of a variable (total_votes) initialized at 0 and add on 1 for each row was read.


 
 

# Initialize a total vote counter.
total_votes = 0
# For each row in the CSV file
for row in reader:
        # Add to the total vote count
        total_votes = total_votes + 1



o	The number of votes and the percentage of total votes for each county in the precinct is shown below

County Votes:
Jefferson: 10.5% (38,855)
Denver: 82.8% (306,055)
Arapahoe: 6.7% (24,801)

Code used to get this result uses a loop to get the county from the county list previously defined

for county in county_list:
        # 6b: Retrieve the county vote count.
        county_vote = county_votes.get(county)

        # 6c: Calculate the percentage of votes for the county.
        county_vote_percentage = float(county_vote) / float(total_votes) * 100  
        # 6d: Print the county results to the terminal.
        county_results = f"{county}: {county_vote_percentage:.1f}% ({county_vote:,})\n"
        # Print the counties to test.
        print(county_results)

o	The county where the most voters cast was Denver (82.8%). It could mean that it is the largest county 

o	The number of votes and the percentage of the total votes each candidate received is shown below
-------------------------
Charles Casper Stockham: 23.0% (85,213)
Diana DeGette: 73.8% (272,892)
Raymon Anthony Doane: 3.1% (11,606)

Code that generates this part of the report is based on a “for” loop in the candidate_votes list where the vote count is retrieved and percentage is calculated
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
        txt_file.write(candidate_results)below. 

o	Diana DeGette won the election as is shown below 
-------------------------
Winner: Diana DeGette
Winning Vote Count: 272,892
Winning Percentage: 73.8%
-------------------------
## Election-Audit Summary: This script can be improved to be used for other elections.

o	Option one: Using a “condition-controlled loop (while loop) to ask the user the name of the input file and output file to save the data”

Insert new lines where a new variable (user_req) used to ask the user whether or not (Y/N) other state is going to be processed is defined. Additionally, user is requested for the input and output files names. Using while as condition loop all the code is executed to generate the report until the user enter “N” as response to the question “Other State Y/N?)
user_req = ("Y")
while(user_req == "Y"):
     
    file_input = input("What's input file name: ")
    file_output = input("What's output file name: ")

# Add a variable to load a file from a path.
file_to_load = os.path.join("..", "Resources", file_input + ".csv")
xxx
xxx
xxx
user_req = input("Other state Y/N?: ")

Request messages 
What's input file name: election_results
What's output file name: new_output_file
-------------------------
Winner: Diana DeGette
Winning Vote Count: 272,892
Winning Percentage: 73.8%
-------------------------
Other state Y/N?: . 
Return to file names request if answer is “Y”, end process when answer is “N”

o	Option two: Using “a repetition statement (for loop) to loop through many input files and using the file name as a parameter for a function”.

A list (state) with all the file names is going to be processed was defined. That list could be populated requesting users for the file names. In this version I am using a list previously populated. 
State = ["Florida", "Oregon", "New York", "Texas", "California"]

Using a “for loop” statement, the name of the file is read from the list from the first one until the last one, take the name of the file as parameter to generate the report required for each state.  
for NameSt in State:

    print(NameSt)
     
        # Add a variable to load a file from a path.
    file_to_load = os.path.join("..", "Resources", NameSt + ".csv")
xxx
xxx
xxx

When the last state in the list is processed the script end
(the same file (renamed) was used in this activity
Florida

Election Results
-------------------------
Total Votes: 369,711
-------------------------

County Votes:
Jefferson: 10.5% (38,855)

Denver: 82.8% (306,055)

Arapahoe: 6.7% (24,801)

-------------------------
Largest County Turnout: Denver
-------------------------

Charles Casper Stockham: 23.0% (85,213)

Diana DeGette: 73.8% (272,892)

Raymon Anthony Doane: 3.1% (11,606)

-------------------------
Winner: Diana DeGette
Winning Vote Count: 272,892
Winning Percentage: 73.8%
-------------------------

Oregon

Election Results
-------------------------
Total Votes: 369,711
-------------------------

County Votes:
Jefferson: 10.5% (38,855)

Denver: 82.8% (306,055)

Arapahoe: 6.7% (24,801)

-------------------------
Largest County Turnout: Denver
-------------------------

Charles Casper Stockham: 23.0% (85,213)

Diana DeGette: 73.8% (272,892)

Raymon Anthony Doane: 3.1% (11,606)

-------------------------
Winner: Diana DeGette
Winning Vote Count: 272,892
Winning Percentage: 73.8%
-------------------------

