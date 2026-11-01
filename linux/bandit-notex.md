# OverTheWire Bandit Notes (Levels 0-10)

Connect: ssh bandit0@bandit.labs.overthewire.org -p 2220
(port 2220 is used instead of the default SSH port 22)

## Level 0
Log in with SSH. SSH lets me run commands on a remote machine over an encrypted connection.

## Level 0 -> 1
cat readme
cat prints a file's content.

## Level 1 -> 2
cat ./-
A file named "-" is read as "standard input" by cat. Using ./ makes it a file path.

## Level 2 -> 3
cat "spaces in this filename"
Spaces split a command into separate words, so the name needs quotes (or \ before each space). Tab completion also handles it.

## Level 3 -> 4
ls -a
cat .hidden
Files starting with a dot are hidden. ls does not show them, ls -a does.

## Level 4 -> 5
file ./*
cat ./-file07   (the file marked "ASCII text")
Most files are binary data. The file command tells the real type of each file without opening it.

## Level 5 -> 6
find . -type f -size 1033c ! -executable
find searches by properties: -type f (files only), -size 1033c (c = bytes), ! -executable (not executable).

## Level 6 -> 7
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
Searching the whole system from / by owner, group and size. 2>/dev/null throws away the "Permission denied" errors.

## Level 7 -> 8
grep millionth data.txt
grep prints only the lines that contain a given word.

## Level 8 -> 9
sort data.txt | uniq -u
sort puts identical lines next to each other, uniq -u keeps lines that appear only once. The pipe | sends the output of one command into the next.

## Level 9 -> 10
strings data.txt | grep "=="
strings extracts human-readable text from binary data. grep then filters the lines I need.

## Level 10 -> 11
base64 -d data.txt
Base64 is an encoding, not encryption. Anyone can decode it, no key needed.

## Commands learned
ssh, ls (-a, -l), cat, cd, file, find, grep, sort, uniq, strings, base64, pipe (|), 2>/dev/null
