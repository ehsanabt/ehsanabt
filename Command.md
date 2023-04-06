## LS

 The command line looks at the directory you are in, and then “lists” all the files and directories inside of it.

 * We have some options for ls command:

-a: lists all contents, including hidden files and directories

-l: (a lowercase “L”) lists all contents of a directory in long format, as well as the file permissions

-t: orders files and directories by the time they were last modified.

* We can use all above options with each others: 

ls -alt

 ## PWD

 stands for “print working directory.” It outputs the name of the directory you are currently in, called the working directory.

 ## CD

 stands for “change directory.

 You can go into a directory with: cd [directory name]
 
 You can move up one directory with: cd ..

## CD ||

* We can use CD command to move to a directory if we know its path:

cd /home/ccuser/workspace/blog/2015/jan/

* We can move up 2 times with below code:

cd ../..

* We can change our directory to another with below command:

cd ../jan
cd ../feb

## mkdir

We can make directory by using this command:

we can go into a directory then make a new directory:

mkdir Ehsan

Or we can make a driectory inside another one without going inside the directory:

mkdir Ehsan/Abtahi

## Touch

* We can create a file by Touch command:

touch keyboard.txt

* We can create a file inside a directory with this command:

touch Ehsan/keyboard.txt

## Cat

The cat command outputs the contents of a specified file.

cat file.txt

* We can also open a file inside a directory with below command:

cat directory/file.txt

## CP

We can copying, moving, and removing files and directories from the command line.

Below command copies the content of file1 into file2

cp file1.txt file2.txt

* We can also copy a file to a destination directory:

cp file1.txt directory1

* We can also choose a new name for copied file:

cp file1.txt directory1/file1-1.txt

* We can also copy list of files in a directory

cp file1.txt file2.txt directory1

* We can use to select all files in a directory
 
cp * directory1

cp *.txt directory1

cp w*.txt directory1

cp *1.txt directory1

## MV

It is used to move file/files from a directory to another

mv file1.txt directory1

* We can move multiple files:

mv file1.txt file2.txt directory1

* mv can be used for rename a file

mv file1.txt file2.txt

## RM

It is used for removing files and directories

rm file1.txt

* -r option allows us to remove a directory and its child directories

rm -r directory1


## ECHO

It is used to add something in a file:

echo "Hello" > file.txt

## >

It is called REDIRECT. It is used for add content of a file into another file.

it overwrites the file's contents

cat file1.txt > file2.txt

## >>

it is used to add some data into a file without loosing the original text

cat file1.txt >> file2.txt

## |  (PipeLine)

It is used for counting lines, words and number of characters in a text file:

cat file1.txt | wc

* We can put above data into a file:

cat file1.txt | wc | cat > file2.txt

## <

Redirect the contents of "gymnastics.txt" as standard input for the cat command.

cat < gymnastics.txt

## Sort

It is used for sorting data of a text file, it doesn't change the file, it only shows sorted data.

sort file1.txt

* We can put sorted data into a new text file:

cat file1.txt | sort > file2.txt

## uniq

It filters out adjacent, duplicate lines in a file.

uniq file1.txt

it is better to sort file before using uniq command:

sort file1.txt | uniq


## grep

It searches a name in a text file:

grep NAME file1.txt

* -i
  
this option used to enable the command to be case insensitive

grep -i NAME file1.txt

* -r

grep -R searches all files in a directory and outputs filenames and lines containing matched results.

* -Rl

searches all files in a directory and outputs only filenames with matched results (so no lines)

## sed

It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to “find and replace.”

sed 's/snow/rain' file1.txt

* s stands for substitution

so above searches file.txt for the word “snow” and replaces it with “rain.” Importantly, the above command will only replace the first instance of “snow” on a line.

* g

g stands for globaly

sed 's/snow/rain/g' file1.txt

searches file1.txt for the word “snow” and replaces it with “rain” globally. This means all instances of “snow” on a line will be turned to “rain.”


* the actual file doesn't change

* -i

it is used for changing the actual file:

sed -i 's/snow/rain/g' file1.txt

## nano

nano is a simple yet powerful tool for editing files in the terminal.

* To open a file in nano: nano <file_name>

* To save changes to a file: Press Ctrl + O and then press Enter

* To exit nano without saving changes: Press Ctrl + X

* To search for a string in a file: Press Ctrl + W

* To move the cursor: Use the arrow keys on your keyboard


## .bash_profile

The .bash_profile is a configuration file used by the Bash.

The Bash shell reads the contents of this file when it starts up and uses it to configure various settings.

users add commands to the .bash_profile file to customize their shell environment.

* making alias new command for PWD
  
1- nano .bash_profile

2- alias pd="pwd"

3- Save (ctrl + o)

4- Close nano (ctrl + x)

5- for activating changes: source .bash_profile

* We can make a variable in .bash_profile:

1- nano .bash_profile

2- export USER="Ehsan Abtahi"

3- Save

4- Close

5- Activate .bash_profile

call variable: echo $USER


## env

The env command stands for “environment,” and returns a list of the environment variables for the current user. like PATH, PWD, HOME, ...




