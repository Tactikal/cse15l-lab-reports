# Lab Report 4

My implementation: [Link](https://github.com/Tactikal/Lab-6-markdown-parser)
Reviewed implementation: [Link](https://github.com/TheJoeship/markdown-parser-other-group)
I used the CommonMark demo site to generate the expected outputs.

## Snippet 1:
Expected Output: 
![image][1]

Test Code:
My Implementation:
![image][2]
Reviewed Implementation:
![image][7]

My Implementation Test Result:
![image][10]
Reviewed Implementation Test Result:
![image][11]

## Snippet 2:
Expected Output: 
![image][3]

Test Code:
My Implementation:
![image][4]
Reviewed Implementation:
![image][8]

My Implementation Test Result:
![image][12]
Reviewed Implementation Test Result:
![image][13]

## Snippet 3:
Expected Output: 
![image][5]

Test Code:
My Implementation:
![image][6]
Reviewed Implementation:
![image][9]

My Implementation Test Result:
![image][14]
Reviewed Implementation Test Result:
![image][15]

## Questions
1. I think that it would require a more involved change, since none of the links are being parsed correctly. The `MarkdownParse.java` file may require a more refined alogorithm for detecting all the links, which is likely to require more than 10 lines of code.
2. To pass the test case, we made sure that nested or loose parentheses/brackets were handled by changing the code so that it kept better track of opening/closing parentheses and brackets in the local variables.
3. To pass the test case, we made sure that the code was able to handle line breaks and/or large spaces smoothly and go over them smoothly, and keep track of parentheses/brackets if they were present. 


[1]:cqcq.JPG 
[2]:zzncn.JPG
[3]:nypo.JPG
[4]:mcmn.JPG
[5]:cqp.JPG
[6]:mlli.JPG
[7]:ccmpmcp.JPG
[8]:bbacl.JPG
[9]:cowo.JPG
[10]:bmmm.JPG
[11]:lkbl.JPG
[12]:ioxoi.JPG
[13]:cacvv.JPG
[14]:pvplk.JPG
[15]:yokml.JPG