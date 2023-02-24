#!/usr/bin/env python3
import argparse;
import random;
import sys;
#Source for words.txt: http://www.mieliestronk.com/corncob_lowercase.txt
#For Reference Only: https://docs.python.org/3/library/argparse.html

#Delete this ltr
"""
#COMMAND LINE SYNTAX
#Note: Each args is optional and may be presented in any order
for opt, arg in opts:
    if opt == "-h" or opt == "--help":
        print('''
usage: xkcdpwgen [-h] [-w WORDS] [-c CAPS] [-n NUMBERS] [-s SYMBOLS]
                
Generate a secure, memorable password using the XKCD method
                
optional arguments:
    -h, --help            show this help message and exit
    -w WORDS, --words WORDS
                          include WORDS words in the password (default=4)
    -c CAPS, --caps CAPS  capitalize the first letter of CAPS random words
                          (default=0)
    -n NUMBERS, --numbers NUMBERS
                          insert NUMBERS random numbers in the password
                          (default=0)
    -s SYMBOLS, --symbols SYMBOLS
                          insert SYMBOLS random symbols in the password
                          (default=0)
                          ''')
"""

#Command Line Syntax and user inputed args
parser = argparse.ArgumentParser(description="Generate a secure, memorable password using the XKCD method")

parser.add_argument('-w', '--words', metavar='WORDS', type=int, 
		    help='include WORDS words in the password (default = 4)', 
		    default=4)

parser.add_argument('-c', '--caps', metavar='CAPS', type=int,
		    help='capitalize the first letter of CAPS random words (default = 0)',
		    default=0)

parser.add_argument('-n', '--numbers', metavar='NUMBERS', type=int,
		    help='insert NUMBERS random numbers into the password (default = 0)',
		    default=0)
		    
parser.add_argument('-s', '--symbols', metavar='SYMBOLS', type=int,
		    help='insert SYMBOLS random symbols into the password (default = 0)',
		    default=0)
		    
args = parser.parse_args()

#Default Values
Caps = args.caps
Nums = args.numbers
Symbls = args.symbols

Pass = []
numbers = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9"]
symbols = ["~", "!", "@", "#", "$", "%", "^", "&", "*", ".", ":", ";"]

#Testing: C:\Users\user1\OneDrive\Desktop\project4\words.txt
f = open("words.txt", "r")
words = list(map(str, f.read().split()))

#Words
for i in range(0, args.words):
  rando = random.randint(0, len(words) - 1)
  Pass.append(words[rando])

#Caps
for i in range(0, Caps):
  Pass[i] = Pass[i].capitalize()

random.shuffle(Pass)

#Handles nums
for i in range(0, Nums): 
  rando = random.randint(0, 9)
  Pass[i] = Pass[i] + str(rando)

random.shuffle(Pass)

#symbls
for i in range(0, Symbls):
  rando = random.randint(0, len(symbols) - 1)
  Pass[i] = Pass[i] + symbols[rando]

random.shuffle(Pass)

print ("".join(Pass))
