# CS166 HW1

For the coding portion of the assignment, I want you to write two programs:
  - Cipher.java -- should be straightforward
  - Classifier.java -- more open-ended
## submission
-- These two files should be contained in the Hw1.zip file
-- do not include class files or project files or any other files.
## compilation
Your code will be compiled from the command line with the lines:
```sh
javac Cipher.java
javac Classifier.java
```
You can assume the grader has a Java 1.6 compiler.
The first program will be run from the command-line with a line of the following format:
```sh
java Cipher action cipher_file.txt text_to_process.txt
```
## detail requirements
#### cipher file
Here action will be one of encrypt or decrypt.
The file cipher_file.txt is a file used to describe a cipher using the format described below
```sh
cipher_type
details on specific cipher
```
the file text_to_process.txt is a file to perform the action on given the cipher described in cipher_file.txt.

Here `cipher_type` can be one of `substitution` or `double-transposition`.
If the first line had `substitution`, then the next line(details on specific cipher) should be a permutation of the letters a-z. For example:
```
hvieopwxyzqrsjklbcdtufgmna
```
This example would mean that, when encrypting, the letter 'a' should be substituted by 'h', the letter 'b' with 'v', etc.
```
hvieopwxyzqrsjklbcdtufgmna
abcdefghijklmnopqrstuvwxyz
```
If cipher_type is `double-transposition`, then the next two lines contain the permutation for the rows and then for the columns.
For example, the lines
```
321
4213
```
would correspond to the double transposition cipher given on page 26 of the book. You can assume the largest double transposition matrix you would need to construct is 9 x 9.

When run from the command line, Cipher should output to stdout the result of doing the given action with regard to the provided cipher in cipher_file.txt on the file text_to_process.txt.
## second program
#### compilation
The second program will be run from the command-line with a line like:
```
java Classifier filename.txt
```
Here `filename.txt` is some file which contains:
- unpunctuated,
- lower-case,
- non-whitespaced,
- UTF-8 English text that has been encrypted with either a substitution or double transposition cipher.

On such an input your program `should output either "substitution" or "double transposition" `depending on whether it thinks a substitution cipher was used or a double transposition was used.

*How you determine which is more likely the case is up to you.*

Hence, this part of the homework is open-ended.

For example, you might try using things like Figure 2.2 in the book (how is this affected by a substitution cipher versus double transposition cipher?
If you can't distinguish on single characters (there is a way to do this using single characters), try character pairs.).

### additional work
In addition, to Cipher.java and Classifier.java, I want you to prepare two text files wiki_first.txt, wiki_last.txt, which are also to be included in Hw1.zip.

To prepare these files, identify the first and last letter of the surname of the youngest member of your team.
For me, Chris Pollett, this would be 'p' and 't'.

Find Wikipedia articles beginning with these two letters. For example, http://en.wikipedia.org/wiki/Potato and http://en.wikipedia.org/wiki/Top_hat , then cut and paste these into either wiki_first.txt or wiki_last.txt, lower-case all letters, and strip all characters other than a through z.
If the resulting file is less than 1 kilobyte choose a different Wikipedia article with that letter.

To receive credit your classifier should be able to work on the two Wikipedia files you create.

In addition, `two bonus points` will be awarded to the top three classifiers from amongst student submissions (this will be judged based on all the wikipedia files submitted).

##### reference
prof.Chris Pollett
CS166 HW1 2012
http://www.cs.sjsu.edu/faculty/pollett/166.3.12f/?Hw1.shtml?Wednesday,%2012-Sep-2012%2022:39:33%20PDT#top


