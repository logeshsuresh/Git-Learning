`git status`

{ On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	Git-Starters.md
	Intro.md }

When you actually work on a project and you have enabled the VCS to be managed by GIT;
there are three regions where any file change that you do might lie.
[WORKING AREA, STAGING AREA, REPOSITORY]

WORKING AREA -> Where you make changes in the file but are not added. These changes will not be reflected in 
                the version. There can be a bunch of files that are not currently handled by GIT. A file 
                in working area is considered not to be in staging area. When we do `git status` and see a 
                bunch of untracked files, they are in the working area. 

STAGING AREA -> What all files are going to be part of the next version. Place where GIT knows what changes
                will be done from the last version to the next version.

{ 
    `git add Intro.md`
    [logeshsuresh@192 GIT-Internals]$ git status
    On branch master

    No commits yet

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
        new file:   Intro.md

    Untracked files:
    (use "git add <file>..." to include in what will be committed)
        Git-Starters.md

    git rm --CACHED Intro.md -> removes the file from the staging area. }

REPOSITORY -> This area actually contains the details of the previous registered version. The files in this 
              area, GIT already manages them and knows their version. 


git add <file> -> moves file from WORKING AREA to STAGING AREA.
git rm --cached <file_name> -> moves the file from the STAGING AREA to WORKING AREA.

To move the file from STAGING AREA to REPOSITORY -> you need to commit.

`commit` -> particular version of the project. Captures the snapshot of the project's staged changes and creates
            a version out of it. 


`git log` -> Lists down all the commits of the repository. 

`git restore` -> Suppose you made changed to a file already in the repository. Rn, the file is in the working 
                 area, in order to undo the changes, you use this command. If the file is in STAGING AREA, this 
                 command will not work. 

`git restore --staged <file_name>` -> Bring the file back in the working area. This only works if changes are 
                                      in your STAGIN AREA.

Difference between git rm and git restore :-
ans: If you want to move the whole file to the untracked state, then we will do git rm, otherwise if we just 
     want the changes to be moved in working area or staging area then we will do git restore.  


`git diff commit1 commit2` -> gives the difference between all commit changes. 

`git commit -m "commit_message"` -> Commit without VIM/Nano editor.
