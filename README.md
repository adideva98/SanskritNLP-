# Synsets-
The Synsets in Synsets SLP1(1).txt have been extracted from the SQL file retrieved from the [Sanskrit Wordnet](http://www.cfilt.iitb.ac.in/wordnet/webswn/wn.php)  
For those wanting the entire SQL database containing the Synsets, Synset Ids , and gloss the file can be downloaded from the Wordnet. 
After downloading the SQL file , open it any text editor or IDE of choice (I have used PyCharm) to make a couple small changes in the SQL file. 
In the beiginning of the SQL file , check the commands given along with the Head and Category columns of the database. Copy the same command and replace the **blob** command found in the synsets and gloss columns with the command you copied.This will ensure the worbench knows what encoding format to use and will be able to display the text in Devnagari script.
The total number of synsets in the Wordnet is 38730 , but the SQL file is updated quite regularly. So check that values starting from 0 to around 145000 appear in the commands. If not referesh the file and try again. 
Then open the MySQL Workbench and create a new schema. Click on the servers tab on the upper left hand side and using the import data tool import this database into your schema. Again ensure that all values appear . This can be checked by checking the Synsets ID, which should begin at 0 and end somewhere around 145000.
The Synsets appear in Devnagari script and to convert it into the English alphabet the Sanscript tool can be used. 
The Synsets in this repo are already in the English alphabet, and can also directly be used. 
