# GitStudyExperiments
Git study and experiments

1.  [Init, Clone, Pull repository](#init_clone_pull)
2.  [Fetch / download objects from repository](#fetch_from_repository)
3.  [Configuration (Global)](#configuration_global)
4.  [Configuration (Local - Repository level)](#configuration_local)
5.  [Show working status](#show_working_status)
6.  [Add | Stage files](#add_stage_files)
7.  [Make commit | Commit changes](#make_commit)
8.  [Check difference](#check_difference)
9.  [List Branches | Check current branch](#list_branches)
10. [Delete](#delete_brances)
11. [Clean](#clean_up)
12. [Log - Commit History](#commit_history)
13. [Git show](#git_show)


<a name="init_clone_pull"></a>
###  Init, Clone, Pull repository
Initialize local git repository

	git init
	
Clone any repository

	git clone 'git@github.com:AndreyTokmakov/GitStudyExperiments.git'

Add remote Name/URL

	git remote add origin 'git@github.com:AndreyTokmakov/GitStudyExperiments.git'
	
Update the current working directory

	git pull origin main	
	git pull --verbose           # Fetch with some debug/verbose output
	git pull --dry-run           # Show what would be done, without making any changes.
	git pull --progress          # Progress status is reported on the standard error stream

<a name="fetch_from_repository"></a>
### Fetch / download objects from repository
Download updates from the repository BUT DO NOT update the local changes - do not overwrite:

	git fetch
	git fetch --verbose         # Fetch with some debug/verbose output
	git fetch --progress        # Progress status is reported on the standard error stream

Show what would be done, without making any changes. (This lets you see what would be fetched without actually downloading data.)

	git fetch --dry-run


<a name="configuration_global"></a>
###  Configuration (Global)

View global configuration:

	git config --global -l	


Ensure your commits are tagged with the correct identity.

	git config --global user.name "Your Name"
	git config --global user.email "username@gmail.com"

Unset (global): (delete global 'user.name' and 'user.email' parameters)

    git config --global --unset user.name
    git config --global --unset user.email


<a name="configuration_local"></a>
###  Configuration (Local - Repository level)

View configuration:

	git config -l

Set 'name' and 'email'

    git config user.name "Your Name"
    git config user.email "username@gmail.com"

<a name="show_working_status"></a>
### Show working status

Show the working tree status: Displays paths that have differences between the index file and the current HEAD commit

	 git status


<a name="add_stage_files"></a>
###  Add | Stage files

Stages All
	git add --all
	git add -A
	git add -A .

Stages New & Modified But Without Deleted [Add all uncommitted files to the repository]

	git add . 

Stages Modified & Deleted But Without New

	git add -u 

add all the txt files in current directory

	git add *.txt 

add all txt files in docs directory

	git add docs/*/txt

add all files in docs directory

	git add docs/

<a name="make_commit"></a>
### Make commit | Commit changes

Commit staged chages:

	git commit

Commit staged chages with comment:

	git commit -m "Some commit message"

Commit staged chages with comment (link with JIRA task):

	git commit -m "TSK-2045: Some commit message"

<a name="check_difference"></a>
### Check differences

Comparison with the last commit

	git diff

Compare two spesific commits:

	git log --oneline    # output a list of commits and their IDs:
	git diff 38bb909 93bb5de


To compare specific files between two branches:</br>Example: compare Utilities.py file from <b>main</b> and <b>develop</b>

	git diff main develop Utilities.py	

<a name="list_branches"></a>
###  List Branches | Check current branch

Check current branch

	git branch

See which branches are available.

	git branch -a

<a name="delete_brances"></a>
### Delete brances

    git branch -D some_network_waiting_utilities                     #  Delete a local branch
    git push origin --delete some_network_waiting_utilities          #  Remove a remote branch 

<a name="clean_up"></a>
### Clean

Quickly remove unwanted files (not tracked by Git)

	git clean -fd

Don’t actually remove anything, just show what would be done

	git clean --dry-run

<a name="commit_history"></a>
### Commit History

Check the detailed changes of each file:

	git log -p

Check statistics:

	git log --stat

Pretty history:

	git log --pretty=format:"%h - %an, %ar : %s" --all

For example, if you want to see which commands changed the text files in the Get source code in October 2008, </br>
authored by 'Junio Hamano' and which were not merge commits, you can run the following command:

	git log --pretty="%h - %s" --author='Junio Hamano' --since="2008-10-01" --before="2008-11-01" --no-merges -- t/

Visualizing the commit history:

	git log --graph --oneline --all

<a name="git_show"></a>
### Git show

Show commit (using git hash) ('git log --oneline')

	git show 390e231  -n 1 --graph
	
see the detailed changes of a specific commit:

	git show 1af17e73721dbe0c40011b82ed4bb1a7dbe3ce29
