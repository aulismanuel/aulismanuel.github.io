---
layout: default
---

## Command line course, fall 2022

I really learned a lot on this course. Before this I only knew the basics of command line, and not even that was intuitive – i needed a cheatsheet for commands like echo, cat and ls.

## Brief list:

+ Week 1: Introduction
+ Week 2: Remote server
+ Week 3: Text processing I
+ Week 4: Text processing II
+ Week 5: File structure & programming I
+ Week 6: File structure & programming II
+ Week 7: Git & Github
+ Week 8: Github Pages
+ Final note / embarrassing disclaimer

![image](https://cdn.newsapi.com.au/image/v1/8791f511b22d3b0abb8b52c575bff083?width=650 "Here's an image!")

## Week 1

We learned the basic commands – how to move in directories and manage them and the files.

## Week 2

We connected to Puhti server and were introduced to the usage of a remote server. We also were introduced with symbolic links.
```
aulismanuel@Aulis-MacBook-Pro homework2_aulismanuel % cat hello_wo*
"Hello, world!"
```


## Week 3

We started to do things with texts: tokenizing, sorting, such stuff. How to make a word frequency list.

A piece of a word list:

```
Nuori
nuorien
nuoriin
nuorimman
nuorin
nuorta
nuorukaishymyään
nuorukaiskasvot
nuoruuden
nuoruudessaan
nuoruutensa
```

## Week 4

Very much sed and regex. We learned to make lists of n-grams, as well as to split text into sentences. (Well, the latter one first, actually.)

A piece of a note I wrote on that week:

```
SPLITTING TEXT INTO SENTENCES

dos2unix			    if needed, if the file is a windows text file with carriage returns in line ends

sed 's/^$/#/'			This adds a hash # to all empty lines.

tr '\n' ' '			  Changes all new lines into single spaces. Now all is just a one very long line.

sed -E 's/([\.?!]) ([A-Z])/\1# \2/g'	    Marks all sentence boundaries with a hash.

sed -E 's/([IVX]\.)#/\1/g'     		        Unmarks Roman numbers.

tr '#' '\n'		    Changes hashes into new lines.

sed 's/^ *//'		  Removes all spaces from beginnings of lines

sed 's/ *$//'	    Removes all spaces from ends of lines

grep -v "^$"			Filters out all empty lines.
     					    -v reverses the grep to omit given pattern, not look for it
```

## Week 5

We learned about configuration files. Personally, I learned a lot on this week about shells in general as I'm using zsh instead of bash. We also made some shell programs.

A simple program, I don't recall anymore if it actually works or not:

```shell
#! /bin/bash

# script: freqlist.sh
# author: Aulis Korva (October 2022)

cat $1 |
dos2unix |
tr -s "[:space:]" "\n" |
tr -d "[:punct:]" |
sort |
uniq -c |
sort -nr > $2
```

## Week 6

We learned about the root user / superuser and sudo commands. We also used Python through the shell, and installed stuff with pip. Finally, we also learned about virtual environments.

```python
import nltk
from nltk.tokenize import word_tokenize
word_tokenize("string") # text string to be tokenized
nltk.pos_tag(word) # Word, or array of words. This makes a tuple with POS tag attached to (each) word

from nltk.stem.wordnet import WordNetLemmatizer
lem = WordNetLemmatizer()
lem.lemmatize("corpora", pos="n")
# 'corpus'
```

## Week 7

This week was all about Git. A comprehensive dive into version controlling and the conventions & posibilities of using Git and Github.

## Week 8

And now we learned how to use Jekyll and how to make a webpage on Github. And how to write markdown!

| This          | is            | a           |
| ------------- |-------------- | ----------- |
| table         | just          | to          |
| fulfill       | the           | requirement |

## Final note

I forgot to branch before so I created a branch just before starting to type this paragraph, and I'll merge back after this. About the CV: I simply refused to make it on Overleaf because I don't see it anywhere near this course's scope. But I put my existing CV online and put a link to the nav bar so I still think I meet the grading criterium here.

Much love! This was kinda fun!
