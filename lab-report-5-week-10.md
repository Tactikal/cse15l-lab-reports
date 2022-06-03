# Lab Report 5

I found the tests that had different results using vimdiff on both results.txt files on the remote machine.
I used the CommonMark demo to generate the expected outputs.

## Test 1: 14.md
[Link](https://raw.githubusercontent.com/nidhidhamnani/markdown-parser/main/test-files/14.md)

**Expected output:**
It should be `[]` because there are no links in 14.md.

**Actual outputs:**
Shared repository:
![image][1]
My repository:
![image][2]

For this test file, only my implementation is correct because it successfully parsed that there were no links.

The issue with the shared implementation is that it incorrectly parses `/foo` as a reference to a URL. The test file contains an improper reference to a URL, but the code cannot determine that the reference is incorrect and treats it as if it were a correct reference. This is the segment of code in the shared implementation that should be fixed:

![image][5]

## Test 2: 194.md
[Link](https://raw.githubusercontent.com/nidhidhamnani/markdown-parser/main/test-files/194.md)

**Expected output:**
It should be `[my_(url)]` since it is formatted as a valid link in 194.md.

**Actual outputs:**
Shared repository:
![image][3]
My repository:
![image][4]

For this test file, neither implementations are correct because neither of them gave the expected url. 

The issue with my implementation is that nothing appears to be returned. This is probably because it is stuck in an infinite loop due to conditions for breaking out of the loop not being met, causing it to never reach the line of code that causes the function to return. This is the segment of code in my implementation that should be fixed:

![image][6]

[1]:ooqoq.JPG
[2]:gogoamg.JPG
[3]:apoergj.JPG
[4]:mmmlll.JPG
[5]:sdckl.JPG
[6]:oooekkf.JPG

