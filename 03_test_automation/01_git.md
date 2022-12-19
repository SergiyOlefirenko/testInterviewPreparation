https://www.atlassian.com/git/tutorials


# What is version control?
Version control, also known as source control, is the practice of tracking and managing changes to software code. Version control systems are software tools that help software teams manage changes to source code over time. 
Version control software keeps track of every modification to the code in a special kind of database. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members.

#### Benefits of version control systems
Version Control Systems (VCS) have seen great improvements over the past few decades and some are better that others. VCS are sometimes known as SCM (Source Code Management) tools or RCS (Revision Control System). One of the most popular VCS tools in use today is called Git. Git is a Distributed VCS, a category known as DVCS, more on that later. Like many of the most popular VCS systems available today, Git is free and open source. Regardless of what they are called, or which system is used, the primary benefits you should expect from version control are as follows:
1. **A complete long-term change history of every files.** This means every change made by many individuals over the years. Changes include the creation and deletion of files as well as edits to their contents. Different VCS tools differ on how well they handle renaming and moving of files. This history should also include the author, date and written notes on the purpose of each change. Having the complete history enables going back to previous versions to help in root cause analysis for bugs and it is crucial when needing to fix problems in older versions of software. If the software is being actively worked on, almost everything can be considered an "older version" of the software.
2. **Branching and merging.** Having team members work concurrently is a no-brainer, but even individuals working on their own can benefit from the ability to work on independent streams of changes. Creating a "branch" in VCS tools keeps multiple streams of work independent from each other shile also providing the facility to merge that work back together, enabling developers to verify that the changes on each branch do not conflict. Many software teams adopt a practice of branching for each feature or perhaps branching for each release, or both. There are many different workflows that teams can choose from when they decide how to make use of branching and merging facilities in VCS.
3. **Traceability.** Being able to trace each change made to the software and connect it to project management and bug tracking software such as Jira, and being able to annotate each change with a message describing the purpose and intent of the change can help not only with root cause analysis and other forensics. Having the annotated history of the code at your fingertips when you are reading the code, trying to understand what it is doing and why it is so designed can enable developers to make correct and harmonious changes that are in accord with the intended long-term design of the system. This can be especially important for working effectively with legacy code and is crucial in enabling developers to estimate future work with any accuracy.

<br/>

# What is Git
By far, the most widely used modern version control system in the  world today is Git. Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds. Having a distributed architecture, Git is an example of a DVCS (hence Distributed Version Control System). In addition to being distributed, Git has been designed with performance, security and flexibility in mind.

## Performance
The raw performance characteristics of Git are very strong when compared to many alternatives. Committing new changes, branching, mergin and comparing past versions are all optimized for performance. The algorithms implemented inside Git take advantage of deep knowledge about common attributes of real source code file trees, how they are usually modified over time and what the access patterns are.
Git is not fooled by the names of the files when determining what the storage and version history of the file tree should be, instead, Git focuses on the file content itself. After all, source files are frequently renamed, split, and rearranged. The object format of Git's repository files uses a combination of delta encoding (storing content differences), compression and explicitly stores directory contents and version metadata objects.

## Security
Git has been designed with the integrity of managed source code as a top priority. The content of the files as well as the true relationships between files and directories, versions, tags and commits, all of these objects in the Git repository are secured with a cryptographically secure hashing algorithm called SHA1. This projects the code and the change history against both accidental and malicious change and ensures that the history is fully traceable.
With Git, you can be sure you have an authentic content history of your source code.
Some other version control systems have no protections against secret alteration at a later date. This can be serious information security bulnerability for any organization that relies on software development.

## Flexibility
One of Git's key design objectives is flexibility. Git is flexible in several respects: in support for various kinds of nonlinear development workflows, in its efficiency in both small and large projects and in its compatibility with many existing systems and protocols. 
Git has been designed to support branching and tagging as first-class citizens (unlike SVN) and operations that affects branches and tags (such as merging or reverting) are also stored as part of the change history. Not all version control systems feature this level of tracking.

<br/>

# Getting Started with Git


## What is a Git repository?
A **Git Repository** is a virtual storage of your project. It allows you to save versions of your code, which you can access when needed.
**To create** a new repo, you'll use the ***git init*** command. ***git init*** is a one-time command you use during the initial setup of a new repo. Executing this command will create a new ***.git*** subdirectory in your current working direcotry. This will also create a new main branch.
**Versioning an existing project with a new git repository.** This example assumes you already have an existing project folder that you would like to create a repo within. You'll first ***cd*** to the root project folder and then execute the ***git init*** command.

>cd /path/to/your/existing/code<br/>
>git init

Posting ***git init*** to an existing project directory will execute the same initialization setup as mentioned above, but scope to that project directory.

> git init <project_directory>


## Cloning an existing repository: git clone
If project has already been set up in a central repository, the clone command is the most common way for users to obtain a local development clone. Like ***git init***, cloning is generally a one-time operation. Once a developer has obtained a working copy, all version control operations are managed through their local repository.

> git clone \<repo_url>

***git clone*** is used to create a copy or clone of remote repositories. You pass ***git clone*** a repository URL. Git supports a few different network protocols and corresponding URL formats.


## git add 
The ***git add*** command adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit. However, ***git add*** doesn't really affects the repository in any significant way - changes are not actually recorded until you run ***git commit***.

The ***git add*** and ***git commit*** commands compose the fundamental Git workflow. These are the two commands that every Git user needs to understand, regardless of their team's collaboration model. They are the means to record versions of a project into the repository's history.

Developing a project revolves around the basic edit/stage/commit pattern. First, you edit your files in the working directory. When you're ready to save a copy of the current state of the project, you stage changes with ***git add***. After you're happy with the staged snapshots, you commit it to the project history with ***git commit***. The ***git reset*** command is used to undo a commit or staged snapshot.


## git commit
The git ***git commit*** command captures a snapshot of the project's currently staged changes. Committed snapshots can be thought of as "safe" versions of a project - Git will never change them unless you explicitly ask it to. 

At a high-level, Git can be thought of as a timeline management utility. Commits are the core building block units of a Git project timeline. Commits can be thought of as snapshots or milestones along the timeline of a Git project. Commits are created with the ***git commit*** command to capture the state of a project at that point in time. Git snapshots are always committed to the local repository. This is fundamentally different from SVN, wherein the working copy is committed to the central repository. In contrast, Git doesn't force you to interact with the central repository until you're ready. Just as the staging area is a buffer between the working directory and the project history, each developer's local repository is a buffer between their contributions and the central repository.

***Common options:***
- *git commit*: commit the staged snapshot. This will launch a text editor prompting you for a commit message. After you've entered a message, save the file and close the editor to create the actual commit.
- *git commit -a*: commit a snapshot of all changes in the working directory. This only includes modifications to tracked files (those that have been added with *git add* at some point in their history).
- *git commit -am "commit message"*: a power user shortcut that combines the *-a* and *-m* options. This combination immediately creates a commit of all the staged changes and takes an inline commit message.
- *git commit --amend*: this option adds another level of functionality to the commit command. Passing this option will modify the last commit. Instead of creating a new commit, staged changes will be added to the previous commit. This command will open up the system's configured text editor and prompt to change the previously specified commit message.


## git diff
Diffing is a function that takes two input data sets and outputs the changes between them. ***git diff*** is a multi-use Git command that when executed runs a diff function on Git data sources. These data sources can be commits, branches, files and more. This document will discuss common invocations of *git diff* and diffing work flow patterns. The *git diff* command is often used along with *git status* and *git log* to analyze the current state of Git repo.


## git stash
***git stash*** temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on. Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit.


## git push
The ***git push*** command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo. It's the counterpart to *git fetch*, but whereas fetching imports commits to local branches, pushig exports commits to remote branches. Remote branches are configured using the *git remote* command. Pushing has the potential to overwrite changes, caution should be taken when pushing. 

***Git push usage***
> git push <remote> <branch>

Push the specified branch to, along with all the necessary commits and internal objects. This creates a local branch in the destination repository. To prevent you from overwriting commits, Git won't let you push when it results in a non-fast-forward merge in the desitnation repository.

> git push \<remote> --force

Same as the above command, but force the push even if it results in a non-fast-forward merge. Do not use the *--force** flag uless you're absolutelly sure you know what you're doing.

> git push \<remote> --all

Push all of your local branches to the secified remote.

> git push \<remote> --tags

Tags are not automatically pushed when you push a branch or use the *--all* option. The *--tags* flag sends all of your local tags to the remote repository.


## git remote
The ***git remote*** command lets you create, view, and delete connections to other repositories. Remote connections are more like bookmarks rather than direct links into other repositories. Instead of providing real-time access to another repository, they serve as convenient names that can be used to reference a not-so-convenient URL. 


## git fetch
The ***git fetch*** command downloads commits, files, and refs from a remote repository into your local repo. Fetching is what you do when you want to see what everybody else has been working on. It's sivilar to *svn update* in that it lets  you see how the central history has progressed, but it doesn't force you to actually merge the changes into your repository. Git isolates fetched content from existing local content; it has absolutely no effect on your local development work. Fetched content has to be explicitly checked out using the *git checkout* command. This makes fetching a safe way to review commits before integrating them with your local repository.

***git fetch commands and options**
> git fetch \<remote>

Fetch all of the branches from the repository. This also downloads all of the required commits and files from the other repository.

> git fetch \<remote> \<branch>

Same as above command, but only fetch the specified branch.

> git fetch --all

A power move which fetches all registered remotes and their branches.

> git fetch --dry-run

The *--dry-run* option will perform a demo run of the command. It will output examples of actions it will take during the fetch but not apply them.


## git pull
The ***git pull*** command is used to fetch and download content from a remote repository and immediately update the local repository to match that content. Merging remote upstream changes into your local repository is a common task in Git-based collaboration work flows. The *git pull* command is actually a combination of two other commands, *git fetch* followed by git merge. In the first stage of operation *git pull* will execute a *git fetch* scoped to the local branch that *HEAD* is pointed at. Once the content is downloaded, *git pull* will enter a merge workflow. A new merge commit will be created and *HEAD* updated to point at the new commit.

***Common options***
> git pull <remote>

Fetch the specified remote's copy of the current branch and immediately merge it into the local copy. This is the same as *git fetch \<remote>* followed by *git merge origin/\<current-branch>*.

> git pull --no-comit \<remote>

Similar to the default invocation, fetches the remote content but does not create a new merge commit.

> git pull --rebase \<remote>

Same as the previous pull instead of using *git merge* to integrate the remote branch with the local one, use *git rebase*. This option can be used to ensure a linear history by preventing unnecessary merge commits. Many developers prefer rebasing over merging, since it's like saying, "I want to put my changes on top of what everybody else has done".

> git pull --verbose

Gives verbose output during a pull which displays the content being downloaded and the merge details.


## git branch
A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, staging area, and project history. New commits are recorded in the history for the current branch, which results in a fork in the history of the project.

The ***git branch*** command lets you create, list, rename, and delete branches. It doesn't let you switch between branches or put a forked history back together again. For this reason, *git branch* is tightly integrated with the *git checkout* and *git merge* commands.

***Common options***
> git branch

List all of the branches in your repository. This is synonymous with *git branch --list*.

> git branch \<branch>

Create a new branch called \<branch>. This does not check out the new branch.

> git branch -d \<branch>

Delete the specified branch. This is a "safe" operation in that Git prevents you from deleting the branch if it has unmerged changes.

> git branch -D \<branch>

Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.

> git branch -m \<branch>

Rename the current branch to *\<branch>*.

> git branch -a

List all remote branches.


## git checkout
In Git terms, a "checkout" is the act of switching between different versions of a target entity. The ***git checkout*** command operates upon three distinct entities: files, commits, and branches. In addition to the definition of "checkout" the phrase "checking out" is commonly used to imply the act of executing the *git checkout* command.

The *git checkout* command lets you navigate between the branches created by *git branch*. Checking out a branch updates the files in the working directory to match the version stored in that branch, and it tells Git to record all new commits on that branch. Think of it as a way to select which line of development you're working on.

***Common options***
> git checkout -b \<new-branch>

Simultaneously creates and checks out *\<new-branch>*. The *-b* option is a convenience flag that tells Git to run *git branch* before running *git checkout \<new-branch>*.

> git checkout -b \<new-branch> \<existing-branch>

By default *git checkout -b* will base the *new-branch* off the current *HEAD*. An optional additional branch parameter can be passed to *git checkout*. In the above example, *\<existing-branch>* is passed which then bases *new-branch* off of *existing-branch* instead of the current *HEAD*.

> git checkout \<branch-name>

Switch to the branch *\<branch-name>*. Executing above command will point *HEAD* to the tip of *\<branch-name>*.


## git merge
***git merge*** will combine multiple sequences of commits into one unified history. In the most frequent use cases, *git merge* is used to combine two branches. The following examples 