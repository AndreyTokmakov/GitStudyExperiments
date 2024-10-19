# GitStudyExperiments
Git study and experiments

1. [Init, Clone, Pull repository](#init_clone_pull)
2. [Configuration (Global)](#configuration_global)
3. [Configuration (Local - Repository level)](#configuration_local)
4. [Add | Stage files](#add_stage_files)
5. [Delete](#delete_brances)
6. [Commit History](#commit_history)


<a name="init_clone_pull"></a>
###  Init, Clone, Pull repository
Initialize local git repository

	git init
	
Clone any repository

	git clone 'git@github.com:AndreyTokmakov/GitStudyExperiments.git'

Add remote Name/URL

	git remote add origin 'git@github.com:AndreyTokmakov/GitStudyExperiments.git'
	
Update the current working directory

	git pull origin master	


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


<a name="delete_brances"></a>
###  Delete brances

    git branch -D some_network_waiting_utilities                     #  Delete a local branch
    git push origin --delete some_network_waiting_utilities          #  Remove a remote branch 

<a name="commit_history"></a>
###  Commit History

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