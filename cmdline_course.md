---
layout: default
---
# Introduction 

<img src="https://i.stack.imgur.com/e1q40.png" alt="Joke about command lines" hspace="45" width="50%" align="right"/> On this page, I would like to present the Command line course and what we have done during this semester. As said in the name of the course, it is a gentle introduction to command line tools for linguists and especially how to operate in a Unix-like environment. Each week, a quiz is aimed to familiarize the students with a new element: regular expressions, installing and running programs from the command line, write basic scripts, work on a remote server… Even if some topics might have been quite challenging, they are now mastered and put into practice with the use of Git and Github, and the creation of this webpage.  
To have a clear overview of the course, there will be different sections corresponding to every week.  

## Week 1

The main objectives of this week were setting up the command line environment and learning basic commands. First, we learned to recognize our username and working directory in our terminal/shell by using respectively the commands `whoami` and `pwd`. Another point we discovered was how to import content from the Internet on our terminal with the command `wget` followed by the URL.  
Finally, the videos introduced us to a number of commands in order to rename and move files or quite applications. Here is the list of some of these commands: 
* `cat filename.txt` and `less filename.txt`: viewing the content of a text file
* `mv filename`: renaming and moving files
* `rm filename`:removing files 
* `mkdir (name of directory)`and `cd (name of directory)`: creating and changing directory
* `q`: quiting `less`  
Finally, the last important point discussed during this week was how to use the text editor Emacs that we can open with this command: `emacs filename.txt`

**What I have learned**: I had never work with Unix or programming in general, so everything was new for me during this week. However, the videos and reading materials were easy to understand and I had quickly learned to set up the environment and to use these commands. 

## Week 2

In the first part of this week, we have learned more about the Unix file system as for example how to copy, remove and move/rename directories with the commands `cp -R`, `rm -R` and `rmdir`. To understand a Unix system, it is also important to know know the root directory and other standard directories that are always present in the and see what they contain. In order to know from where a program/command is executed, the command `which (name of the program/command)` is handful.  
The second module of the week was about processes, as every team we run a program or a command a new process is started. To see the running processes, we use the command `top` that we need to exit ourselves with **CTRL+C**. We also saw the differences between foreground and background processes. In the first case, bash waits the end of the process and prints its output in the command line window before showing back the prompt symbol while in the second case bash returns to us immediately while the process is running in the background. By default, the process is run in the foreground and to run it in the background, we need to add an ampersand (&). Here is an example:  
* Process in the foreground: `sleep 5`
* Process in the background: `sleep 10`  
Finally, we saw how to connect, work and transfer files from a remote server. It is common to work on remote servers as it provides us much better computational resources and memory space than our own computer.  

**What I have learned**: As in the previous week, everything was new for me. Although it was a bit more difficult this week, I managed to learn the different commands and to us all the tools.  
## Week 3

The week 3 focused on text processing tools in Unix and different character encodings. In terms of encodings, we learned how to convert a text file in Latin-1 into the most popular character encoding in use currently, UTF-8; the command to accomplish this task is `dos2unix filename.txt`.  
The most important module of the week was learning the command `egrep`, which is used to search for lines in a text files, as well as some useful regular expressions that are a way to specify a search criterion very flexibly. In the following table, we have some examples of regular expressions.  

| Regular expressions | Signification     |
|:-------------------:|:-----------------:|
|`egrep "^..$" filename.txt` |Print all lines with exactly 2 characters|
|`egrep "^[aA] filename.txt`|Print all words starting with a lowercase "a" or uppercase "A"|
|`egrep "^(..)*$" filename.txt` |Print all words with an even number of characters|

Finally, we had a look at formatted text files that are text files organized in terms of columns similar to an Excel document. It is used to keep tabular data and the most common form is the comma-separated-values format (csv).  

**What I have learned**: This material was very challenging for me. At the beginning, I didn’t understand at all the regular expressions as well as the formatted text files, but with practice it has become easier. Now, I feel I understand quite well how `egrep` works.

## Week 4

In week 4, we learned more about text processing using Unix commands in order to accomplish linguistically relevant tasks. Indeed, we worked on the creation of a frequency list (which gives the frequencies of each word type in a text), as well as on sentence per line text file and N-grams. Here are some relevant commands to execute these tasks: 
* `sort filename.txt`: sorting the lines of a text in alphabetical order
* `uniq filename.txt`: copying the input data and keeping only one copy of consecutive identical lines  

Moreover, we discovered another handful tool to edit files on the command line: sed, short for stream editor, quickly edit files without opening them. It is mostly used for finding and replacing strings, as well as for insertion, deletion, search, and other common requirements. Here are some examples of sed uses: 
* `sed “s/cat/dog/2” filename.txt`: replacing the second occurrence of the word “cat” with “dog” in a line.
* `sed “2 d” filename.txt`: deleting the second line of the text file.  

Finally, the material of this week also put emphasis on how to combine simple commands into more complex command pipelines in order to avoid many intermediate files. Here are some examples of pipelines: 
* `cat filename.freq|grep "[02468]"|wc -l`: counting the number of tokens that occur an even number of times in the file
* `cat filename.txt | tr -s '\n\t\r ' '\n' | tr -dc "A-Za-z0-9'\n" | sort | uniq -c | sort -nr | grep "intellect"`: counting the number of occurences of the word "intellect in the text file by executing at the same time several simple commands such as `tr`, `sort`and `uniq`.

**What I have learned**: This week I understood better how to use tools for text processing. The most challenging part of the new material was the combination of simple commands into more complex command pipelines, but with practice it becomes more and more easier.

## Week 5

This week focused on three notions: the scripts, the environment variables and the configuration files. The first ones are a very useful way to use commands in Unix without needing to repeat it every time. Indeed, we can store a pipeline of Unix commands in one determined script that can be used several times. A script has the format **filename.sh** and is a user-defined command and can be used by different users depending on the permissions given to the users. The command `chmod` defines the permissions of a script according to the flags that are used. Here is an example:  
* If we run the command `chmod u+x filename.sh`, it gives the user the permission of reading and writing the filename.sh.

The second point of the week was about environment variables. Some common settings are kept in this environment variables and might be interesting for all the processes. One of the most important environment variables is _PATH_: it contains a list of directories that programs search to find other programs. Indeed, _PATH_ contains a list of possible directories and when we give a command the bash will go through this list in order to search for the program. To set a new value for an environment variable, we can use the command `export`.  
Finally, we saw the configuration files that can be used to set an environment variable permanently. The most common configuration files on MacOs is **~/.bash_profile** and by modifying this file we can modify the value of the _PATH_ as well as the elements of the prompt (current date, color…)  

**What I have learned**: What I preferred this week was the configuration files and the possibility to change the appearance of the prompt. 

## Week 6

The first element of this week was installing software. In order to install software in our system, we need to have the privileges of the administrator user, called the root user in Unix. We have two different commands to accomplish this:  
* su`: becoming the root user permanently (after entering the root password)
* `sudo (any other command)`: becoming the root user for the duration of one single command, after entering the user password 

We also learned the notion of software libraries and software dependencies, as well as package managers. The latter do the lifting part of the software installations by taking care of the “dependencies” of a software. When you install a software with a package manager, it analyses all the necessary dependencies and updates them, and finally installs the required software. The most common package managers are **apt-get** in Linux systems and **homebrew** in MacOs.  
The last point of the week was the **makefile** used to build complex projects. Indeed, **make** is ideal for running the same scripts on a number of files, for example a collection of texts.  

**What I have learned**: After completing the quiz of this week, I can install software and programs using package managers, but I still have difficulties to understand **makefiles**.

## Week 7

This week focused on version control which is an integral part of developing projects. It allows us to keep multiple versions of a file and to make changes without losing previous processes. It becomes even more useful when different developers are working on a project. The most widely used version control system today is Git, notable provided by the platform Github. We learned this in order to create on our website on Github.  
First, we created a Github account and learned how to create a Github repository. Then, we installed **Jekyll**, a static site generator that is useful for rapid prototyping. Indeed, Github pages work by making changes on the local repository and then pushing them on the repository on Github, which can take some minutes. Jekyll converts the content of the local repository to a static site format to have a quick overview of the webpage on the computer. Here is an example of how to use Jekyll:  
* While we are working in our local repository, we can run the command `bundle exec jekyll serve` that will generate a temporary http address on which we can have an overview of the website. To cut the command, we need to execute `ctrl-c`.  

Finally, we learned **Markdown** that is the language used on GitHub pages.

**What I learned**: Unlike the previous quizzes that I found challenging, I really like this one and the creation of the Github page: it puts into practice everything we’ve learned in the course and it becomes more concret.

## My overall impression of the course

As a student of modern laguages, I had never heard of command lines or Unix system before the course and it was very difficult for me to understand at the beginning. But today, after more than two months of work and learning, I am happy to have taken that course and I have learned a lot. And last but not least, I have even discovered than command lines can be really cool sometimes!  
To conclude, I would like to share with you this webpage that shows some [funny possibilities of the command lines](https://www.tecmint.com/20-funny-commands-of-linux-or-linux-is-fun-in-terminal/).