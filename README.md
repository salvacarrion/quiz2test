# Quiz2Test

Quiz2Test allows you to parse multiple choice quizzes in raw formats (txt, pdfs, jpg,...), to structured formats such 
as json, anki, etc.


## Requirements

- Python3


## Installation

Open the terminal, go to the folder of this package and type:

On Ubuntu/Debian/Mac OS:

```
python3 setup.py install --user
```

On Windows:

```
py setup.py install --user
```


## Usage

By the default, quiz2test searches in the folder `raw/` (create it) for files to parse. Then it save the parsed files at `parsed`.

Type `quiz2test` in the terminal to see the available options:

```
usage: main.py [-h] [-a {parse,read,convert2anki}] [-i INPUT] [-o OUTPUT]
               [-t TOKEN] [-s] [-e EXCLUDE_WORDS]

optional arguments:
  -h, --help            show this help message and exit
  -a {parse,read,convert2anki}, --action {parse,read,convert2anki}
                        shows output
  -i INPUT, --input INPUT
                        File or folder to search for the raw exams
  -o OUTPUT, --output OUTPUT
                        File or folder to save for the parsed exams
  -t TOKEN, --token TOKEN
                        Token used to split questions and answers
  -s, --show_correct    Show correct answer
  -e EXCLUDE_WORDS, --exclude_words EXCLUDE_WORDS
                        File with excluded words
```

## Example

### Parse

**Command:**
´´´
quiz2test --action parse --input examples/raw --token "======"
´´´

**Input file (`examples/raw/demo.txt`):**
´´´
This is a demo in order to 
show how the program works
  
1. Can quiz2test manage multiple choice questions with weird formats?
a. Yes! That's its purpose!
B) no, it can't
c	it depends...
D- who knows????


2. Can quiz2test deal with
broken lines
?
a. Maybe...
b) Yes, but format the "letter [symbol]
sentence is required
c	No, that's imposible
d) Yes, but only for text files


3) Can we use a list of banned words?
A) No
B) I've doubted it
C) Yes, just creat a "banned.txt" file with one word or sentence per line
d) Maybe in the future...

===
Solutions:
1. A
2 - b
´´´


**View result:**

````
quiz2test --action read 
´´´

```
```