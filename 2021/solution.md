# Advent of Code 2021
## Solutions using Bash and APL

**Note:** 
- Each Day uses seperate input. 
- First the input is copied to a text file name *day{number}-input.txt}* where *{number}* is the current day number.
- The input is pre-processed into an array by a bash script and copied to system clipboard.
- In APL, the pre-processed input array is used by writing: `Input ← {copied}` where *{copied}* is the 
  pre-processed array that was previously copied to clipboard by bash.

## Day 1
**Bash:** `cat day1-input.txt | tr '\n' ' ' | xclip -selection clipboard`

**APL:**
```
⍝ Input is an array of numbers
+/2</Input      ⍝ Part 1
+/2</3+/Input   ⍝ Part 2
```

## Day 2
**Bash:** `awk 'BEGIN {ORS=" "} NF {print "(\x27" $1 "\x27 " $2 ")"}' day2-input.txt | xclip -selection clipboard`

**APL:**
```
A ← ↑Input
+/A[;2]×(1 0j¯1 0j1)[('forward' 'up' 'down')⍳A[;1]]
```