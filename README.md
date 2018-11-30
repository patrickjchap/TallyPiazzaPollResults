# NAME
	TallyPiazzaPollResults -- Builds a CSV file from downloaded Piazza polls

## SYNOPSIS
	TallyPiazzaPollResults pollFile [...] -a pollFileAnswer [...]

## DESCRIPTION
	TallyPiazzaPollResults processes one or more downloaded Piazza poll statistics files
	and outputs a CSV file summarizing their results.  The resulting CSV is organized like:

	    studentKey         		   	 pollFileName1 pollFileName2 ... participated awarded
	    student1@u.boisestate.edu		     4	         3		      2         2
	    student2@u.boisestate.edu	   	     2			              1         0
	    student3@u.boisestate.edu		     4		 3	              2	        2

	 ...with a header row followed by one row of data for each student who took any of
	 the specified polls.  Each student row has a column for that student's eMail address
	 and each of the specified polls.  The student's numeric selection is displayed if that
	 student participated in a poll, else their entry for that poll is blank.  In the example
	 above, student1 selected choice 4 in poll1 and 3 in poll2.  Student2 selected
	 choice 2 in poll1 but did not participate in poll2.
	 
	 Students who don't participate in any of the specified polls will not have a row entry.

	 The participated column simply contains just the total count of polls that a student
	 participated in. The awarded column represents the total number of answers that were
	 correct by the student.

	 All entries in the CSV are separated by commas.

## TECHNOLOGY
* Requires C++11
* Created and tested in Ubuntu

## POTENTIAL FUTURE WORK
* TallyPiazzaPollResults.cpp main method is somewhat 'hacked' and should probably be refactored
