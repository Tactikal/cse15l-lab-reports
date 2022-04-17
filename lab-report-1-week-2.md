# Logging Into A Course Specific Account On ieng6

## Step 1: Installing VSCode
* Go to the VSCode [Website][1] and download the correct installation file for your system.
The page should look like this:
![image][2]

* Then, start the program. You should see a window that looks like this:
![image][3]

Once you do, you are good to go for this step.

## Step 2: Starting the Remote Connection
* If you are using Windows, you will first need to install OpenSSH, which connects your computer to other computers that have course-specific accounts as well.
You can find it here: [OpenSSH][4]
* Use the UCSD Account Lookup Service to find your course-specific account name: [ALS][5]
* Then, open a new terminal in VSCode using the (Ctrl + `) or (Terminal - New Terminal) option. 
Enter this command into the terminal, with the '~' replaced by the chracters of your course-specific account name: 
```
$ ssh cs15lsp22zz@ieng6.ucsd.edu
```
If this is your first time connecting to the server, you may see a message stating that the authencity of the host can't be established and asking if you are sure you want to connect to the server. It is safe to answer yes and connect to the server if you are doing so for the time, but be careful when this message appears on a server you connect to often. 
* Type yes and press enter, then enter the password you use to login to your general UCSD account.
After logging in, you should see a screen that looks like this: ![image][6]
This means that you were able to successfully log into a remote machine.

## Step 3: Running Commands
* Try experimenting with some basic commands: `cd, ls, pwd, mkdir, cp`. Run them both on your personal computer and the remote computer. 
* Other commands you can try are: `cd ~, cd, ls -lat, ls -a, cp /home/linux/ieng6/cs15lsp22/public/hello.txt ~/, cat /home/linux/ieng6/cs15lsp22/public/hello.txt`
An example of these commands being run can be found here: ![image][7]
* Once you are done, you can log out using (Ctrl + D) or by running the command `exit`.

## Step 4: Moving Files
* We can use the command `scp` to copy files back and forth between computers; it is always run from the client (your personal computer). 
* Create a file called `WhereAmI.java` and paste the following code into it:
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}

```
To test it, run it using javac and java on your computer first. 
* Then, in the same terminal from the directory `WhereAmI.java` is in, run the command `scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/`. You should be prompted for a password. 
* Log into ieng6 with ssh, and run `ls`. You should be able to see `WhereAmI.java` in the home directory, as well as run it on the remote computer using javac and java. 

## Step 5: SSH Keys
SSH keys, created by the ssh-keygen program, help make the remote login process more efficient by creating a pair of files (public key stored on the server, private key stored in a client location) used in place of the password during login.
* Run `$ ssh-keygen` to set up this process. If you are using Windows, you should run `ssh-keygen -t ed25519`. After running this command, you will see something like this: ![image][8]
This process created two files: a private key (stored in the `id_rsa` file), and a public key (stored in the `id_rsa.pub` file) in the `.ssh` directory on your computer. Now you need to copy the public key to the `.ssh` directory on the remote computer. 
* Log into the remote computer using ssh as usual, and run `$ mkdir .ssh` to create the `.ssh` directory if it does not already exist. 
The result in the terminal should look like this: ![image][9]
Logout before moving onto the next step.

* Then, run `$ scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys` on your computer, filling in your information where necessary. Use your username/path from the command in the first step. 
The output should look like this: ![image][10]

* If the previous step was successful, you should now be able to log into the remote computer without having to input your password.
Here is an example of login using the key: ![image][11]

## Step 6: Remote Running Optimization
To save even more time on logging into a remote machine and accessing its information, there are several tricks you can use:

1. Writing a command in quotes at the end of an ssh command to run it on the remote server and logout immediately after
Example: `$ ssh cs15lsp22zz@ieng6.ucsd.edu "ls"`
Output: ![image][12]

2. Using semicolons to separate and run multiple commands in a single terminal line
Example: `$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

3. Using the up arrow on the keyboard to quickly recall previously run commands



























[1]: https://code.visualstudio.com/download
[2]: e2f.JPG
[3]: qow.JPG
[4]: https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse
[5]: https://sdacs.ucsd.edu/~icc/index.php
[6]: qoc.JPG
[7]: fqx.JPG
[8]: vnmv.JPG
[9]: fwfw.JPG
[10]: vov.JPG
[11]: vnai.JPG
[12]: oic.JPG
