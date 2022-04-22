# Lab 3: Fixing Bugs

## Code Change #1:
Here is the changed code:
![image][1]

Here is the link to the tester file containing the error:
[TestFile:][2]

Here is the output of the MarkdownParser version that contains an error:
![image][3]

The input with an error consists of adding an image (which also contains brackets) to the tester file. Since the code parses links based on brackets, the image is read as a link. The symptom is the image link being added to the array since it is being treated as a link.


## Code Change #2:
Here is the changed code:
![image][4]

Here is the link to the tester file containing the error:
[TestFile:][5]

Here is the output of the MarkdownParser version that contains an error:
![image][6]

The input with an error has an image in it, as well as a link that has a missing parenthesis. This causes the code to return -1 and throw a StringIndexOutOfBoundsException because it is unable to locate the ending parenthesis. The symptom is the exception being thrown, as well as the program being unable to run past that line of code.


## Code Change #3:
Here is the changed code:
![image][7]

Here is the link to the tester file containing the error:
[TestFile:][8]

Here is the output of the MarkdownParser version that contains an error:
![image][9]

The input with an error has links that include parentheses, and is also missing an ending parenthesis. Although the code returns the links in the array, they are not properly formatted and look odd. The symptom is that the links in the returned array are missing their ending parentheses.




[1]: gvev.JPG
[2]: https://github.com/TheJoeship/markdown-parser-fork/blob/c7f113e692a4fcd7437ae8a3c43b5f536d82497d/test-file3.md
[3]: wqcq.JPG
[4]: xqxq.JPG
[5]: https://github.com/emaresmoreno/markdown-parser/blob/9b4a2f39aa51cdd2cd42d9f0202ee98d0a078ef2/test-file.md
[6]: bwn.JPG
[7]: noin.JPG
[8]: https://github.com/cindy4127/markdown-parser/blob/199ca3258f978ee3e2c639afdc383765f3129abf/test-file2.md
[9]: ccqc.JPG