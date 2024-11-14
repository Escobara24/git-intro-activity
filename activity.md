Git Intro Activity
==================

A. Form teams
Teammate Chase: Chase and Me(Alexander Escobar). Chase is the Driver while I navigate

Form a 2-person team. Try to find someone who uses the same platform as you (e.g., Windows, Linux, etc.). If you can't, that's fine. If you are the odd-person-out, join a team of 2.

Assign the following roles to the members of your team. If you are in a
team of 2, assign the recorder and navigator roles to the same person.

Roles:

-   Driver: Creates and maintains a local git repository.

-   Navigator: Reads instructions and records answers.

3rd person role (if you have a 3-person team):

-   Quality Assurance Person: Ensures instructions are being carried out correctly, answers are clear, and looks for ways for the team to work together more effectively.

You will be rotating roles. Your instructor will let you know when to switch roles. Switching roles requires switching computers. So, plan accordingly.


B. Setup
We created a google doc four our team and copied it

1. Create and share a shared document (Google Doc, Etherpad, etc.) for your team.
2. Copy and paste this document into your shared document.

C. Download and install Git
We both downloaded it on windows

Download and install Git for your operating system:

-   <https://git-scm.com/downloads>

Starting a terminal:

-   **Windows**:

    -   git-bash.exe (Linux style commands)

    -   git-cmd.exe (Windows style commands)

-   **Mac OSX:** Finder -&gt; Applications -&gt; Utilities -&gt;
    Terminal.app

-   **Linux:** will vary depending on your window manager

D. Getting help
---------------

Run the following commands.

    git help
    git help -ag
    git help init

1.  What does `git help` do?

    It displays general help for Git commands, letting us know where to start and what commands are available


    ```

2.  What does `-ag` cause `git help` to do?

    This lists all available Git commans in detial



    ```

E. Identify yourself
--------------------

Run the following commands, replacing BOGUS NAME and BOGUS@EMAIL with
your name and email.

    git config --global user.name 'BOGUS NAME'
    git config --global user.email 'BOGUS@EMAIL'

WARNING: The name and email you give will be listed on each commit you make.
If this repository is ever published, your name and email on every commit
will be too. Also, if you are working on a shared computer, you should
consider changing this configuration before you walk away.


1.  What are these commands doing?

    They set the user’s name and email for commits made in the repository, which shows who made each change.



    ```

2.  What is the purpose of `--global`?

   The `--global` option applies these settings for every Git repository on this machine



    ```

F. Create a repository
----------------------

From the command line, run the following commands.

```
mkdir first_project
cd first_project
```

1.  By default any file that starts with `.` is hidden. How do you
    display a hidden file?

    Use `ls -a` in the terminal to list all files


    ```

2. Run this command to show the hidden files in the current directory. Are there any?

    No hidden files show up right after creating the directory.



    ```

3. Now run the following command.

    ```
    git init
    ```


4. Check for hidden files again.  What was created by `git init`?

    The `.git` folder was created, which contains all the configuration and history for this Git repository.



    ```


3.  What do you think would happen if you delete `.git`?

    Deleting `.git` removes Git tracking from the folder, essentially turning it back into a regular directory



    ```

4.  Using your observations to the previous questions, answer the following.
    You find an old project on your hard drive. You do not remember if
    it is a under version control. What could you look for to determine
    if the project is being managed using Git?

    `.git` folder in the project directory. If it's there, the project is managed by Git.



    ```

G. Basic commands
-----------------

Use a plain text editor to create `names.txt` inside the `first_project`
folder. Put the names of your team in the file. Save and exit.

Run `git status` before and after each of these commands.

    git add names.txt
    git commit –m “Add our names.”
    git log

1.  What kind of information does `git status` report?

    It shows the state of the working directory and staging area



    ```

2.  What does `git add names.txt` do?

    It stages `names.txt`, preparing it to be included in the next commit.



    ```

3.  What does `git commit -m "Add our names."` do?

    It commits the staged changes, saving them with a message describing what was changed.



    ```

Use a plain text editor to create the following files:

-   `birthdays.txt` - Put your birthdays in this file.

-   `movies.txt` - Put the last movie each of you watched in alphabetical order.

Run `git status` before and after each of these commands.

    git add .
    git commit		Note:  Commit will open the vim editor; write a multi-line commit
						   message, save and quit (press esc and then type :wq).
    git log

4.  What does `git add .` do? What do you think `.` means?

    The `.` stages all changed files in the current directory, making them ready for commit.



    ```

5.  What does `git commit` (without -m) do?

    It opens the default editor to write a multi-line commit message.



    ```

6.  If you want to write a more detailed commit message (which is
    good practice) what command would you use?

    Use `git commit` without `-m` to open the editor for a detailed message.



    ```

7.  What does `git log` do?

    It shows the history of commits in the repository, including messages, author, and timestamps.



    ```


H. Stage/Cache/Index
--------------------

Do the following:

-   Modify `names.txt` so that names are listed in *Last, First* format,
    one per line.

-   Modify `movies.txt` so they are in reverse alphabetical order
    by title.

-   Create a new file `foods.txt` that contains your favorite foods (one
    for each team member).

Run the following commands:

    git add names.txt
    git status

1.  Categorize the state of each file by writing each file name under the appropriate state below. Compose a definition for each state.

    **Staged**

    names.txt (staged for commit)



    ```

    **Unstaged**

    movies.txt (modified but not staged) 



    ```

    **Untracked**

    foods.txt (new file, not staged) 



    ```

1.  If you run `git commit` what changes will be committed (***don't do
    it***)?

    Only the changes to `names.txt` will be committed, as it's the only staged file.



    ```

2.  What command do you run to stage changes?

    Use `git add [filename]` to stage changes.



    ```

3.  What command do you run to unstage changes?

    Use `git reset [filename]` to unstage changes.



    ```

Run the following commands:

    git diff
    git diff --cached

1.  What does `git diff` display?

    It shows unstaged changes between the working directory and the staging area.



    ```

2.  What does `git diff --cached` display?

    It shows changes that are staged and ready to be committed.



    ```

3.  Formulate a sequence of commands to unstage changes to `names.txt`,
    and stage the changes to `movies.txt`. Execute your commands and
    confirm they worked.

    git reset names.txt
    git it add movies.txt



    ```

4.  Edit `movies.txt`, change any one of the movies, and save it. Then
    run `git status`. What do you observe? Explain what you think is
    going on.

    ````git statusnow showsmovies.txt` as both staged (with old changes) and unstaged (with new changes)



    ```

5.  Delete `names.txt`. Then run `git status`. What do you observe?
    Explain what you think is going on.

    Git notices the deletion and marks it as a change to be staged.



    ```

6.  Rename `movies.txt` to `last-movies`. Run `git status`. Observe
    and explain.

    Git recognizes the rename as a change, showing `movies.txt` as deleted and `last-movies` as untracked.



    ```

7.  Formulate a sequence of commands to stage all changes including the
    untracked file and commit (with any reasonable message you like).
    Execute them.

    git add .
    git commit -m "Add and modify files as needed."



    ```

8.  In Git vernacular, `index`, `cache`, and `stage` all refer to the
    same thing. What does it hold?

    It holds changes that are staged and ready to be committed.





    ```

9.  Why have a `stage`? Why not just commit all changes since the last
    commit?

    Staging lets us selectively commit changes, giving more control over what goes into each commit.




    ```

I. Undo
-------

Run the following commands:

    git log
    git status
    git reset --soft "HEAD^"
    git log
    git status

1.  What does `git reset --soft ``"HEAD^" `do?

    It moves `HEAD` back one commit, keeping changes staged.




    ```

Run the following commands:

    git commit –m "Redo."
    git log
    git status
    git reset --hard "HEAD^"
    git log
    git status

1.  What does `git reset --hard "HEAD^"`` `do?

    It moves `HEAD` back one commit and discards all changes from that commit.




    ```

2.  What is the difference between `--hard` and `--soft`?

    ````--softkeeps changes staged, while--hard` removes them entirely.```




    ```

3.  What do you think `HEAD` means?

    It represents the current commit or snapshot that we’re working from.



    ```

4.  What do you think `HEAD^` means?

    It refers to the commit just before the current `HEAD` commit.



    ```

J. Helpful resources
--------------------

-   <https://git-scm.com/doc>

-   <https://www.atlassian.com/git/tutorials/>

-   <https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf>

K. Copyright and Licensing
--------------------------

Copyright 2016, Darci Burdge and Stoney Jackson SOME RIGHTS RESERVED

This work is licensed under the Creative Commons Attribution-ShareAlike
4.0 International License. To view a copy of this license, visit
<http://creativecommons.org/licenses/by-sa/4.0/> .
