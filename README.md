# stage0.sh
# HackBio Genomics Task0
#BIOCOMPUTING TASK1:
#A simple Bash program where my first name and last name are assigned to different variables, and the script prints out my full name.
Firstname="Paschal"
Lastname="Ugwu"
echo $Firstname $Lastname

#BIOCOMPUTING TASK2:
A version where the strings are printed on the same line and a version where the strings are printed on different lines.
Firstname="Paschal"
Lastname="Ugwu"
echo $Firstname
echo $Lastname
echo $Firstname $Lastname

#BIOCOMPUTING TASK3:
#Login to the server
ugwupaschal@gmail.com

#Create a new folder titled your name
mkdir ugwu

#Create another new directory titled biocompute and change to that directory with one line of command
mkdir biocompute && cd biocompute

#Download these 3 files:
wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna
wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk

#OH! You made a mistake. You have to move the .fna file to the folder titled your name directly. (Do this with one command. Hint: See our cheatsheet)
mv wildtype.fna ../ugwu/

#OH No! The gbk file is a duplicate, they are actually the same thing. Please delete it.
rm wildtype.gbk.1

#The .fna file is actually from a bacteria, and it should definitely have a TATA (tata) box for initiating gene transcription. The molecular biologist is trying to understand the implication of dual TATA sequences. The files got mixed up and we are not sure which is wildtype and which is mutant. The mutant should have “tatatata” while the normal should have just “tata”. Can you confirm if the file is mutant or wild type
grep ‘tatatata’ wildtype.fna

#If it is mutant, print all the lines that show it is a mutant into a new file
grep ‘tatatata’ wildtype.fna > mutant

#Clear your terminal space and print all the commands you have used today.
clear &$ & history

#List the files in the two folders and share a screenshot of your terminal below
ls && ls ../biocompute

#Bonus Task: Exit the terminal
$ exit


#BIOCOMPUTING TASK4:
#Use the figlet command to draw a graphical representation of your name.
sudo apt-get install figlet
figlet Ugwu Paschal

#In your home directory, create a folder called compare.
mkdir compare

#Download this file [5MB] into your the compare directory:
wget https://www.bioinformatics.babraham.ac.uk/training/Introduction%20to%20Unix/unix_intro_data.tar.gz

#Unzip using gunzip command
gunzip -v unix_intro_data.tar.gz

#Then, untar the .tar file with tar command
rm -rf compare
tar -tvf unix_intro_data.tar
tar -xvf unix_intro_data.tar

#Get into seqmonk_genomes/Saccharomyces cerevisiae/EF4 and identify the rRNAs present in Mito.dat.
less seqmonk_genomes/Saccharomyces cerevisiae/EF4
grep mito.dat

#Using cp copy Mito.dat into the compare directory.
cp mito.dat ../compare

#Use nano to effect the following edits:Change Mito to Mitochondrion in the ID and AC header lines, Save the file and exit nano, Rename the file from Mito.dat to Mitochondrion.txt
nano
CTRL -\

#In task 3, in your compare directory, cd into FastQ_Data directory. Calculate the total number of lines in lane8_DD_P4_TTAGGC_L008_R1.fastq.gz. Print the total number of lines in all fastq.gz files and save it as a new file.
cd FastQ_Data
ls /lane8_DD_P4_TTAGGC_L008_R1.fastq.gz | wc - l
ls /FastQ_Data | wc - l


