# clash_of_code_script
Script adapted for 42 Wolfsburg students

Token has to be renewed; it´s not automatized right now, on to do list ;)

# **Usage**

To install the script:

	git clone : https://github.com/42wolfsburg/CoC_script.git 

Set up API in .env file :

	API42_ID=xxx
	API42_SECRET=xxx

To launch the script:

	./all_in_1.sh "contest1" "contest2" [...] "contestN"

With "contestX" being the contest handle.

**The contest handle is the last part of the URL of the contest. Should be around 39 characters long.**

Example:

>./all_in_1.sh 2243934bca01cf9496f225c8b0b3373fa53f2c9   	[...]

Will produce 1 round file for each contest, and one ranking.csv file with final score.


## **Detailed use**

To launch the harvester script:

	python3 harvest.py "Contest handle" "output file name" (the .csv is added automatically)

The contest handle is the last part of the URL of the contest. Should be 39 characters long.

Example:

>python3 harvest.py "22499132d096a88cf6d6bcdf606295e28bcd6c0" "round1"

This command will output the top 20, and put the result in 'round1.csv'


It is possible to add points for each place in the ranking.
In order to do this you have to use or create "score.cfg".

"score.cfg" is formatted as below:

It **has** to be formatted like this:

	//place,points
	1,100
	2,90
	3,80
	...

On the exact same basis, you have the pseudo.cfg to map a CodinGame pseudo to a login.

It **has** to be formatted the same way:

	//CodinGame Pseudo, login
	lmartinUwU,lmartin
	dArkGam3rxXx,nfascia
	lostarkaddict,pdubois
	...

Once you have finished all rounds, you have a final script   (final_ranking.py) that will take all the "roundsX.csv" files and produce one final ranking based on the score of each person for each round.

You can launch it like this:

	python3 final_ranking.py round1.csv round2.csv round3.csv [...] roundN.csv
