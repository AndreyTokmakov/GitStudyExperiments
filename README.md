# GitStudyExperiments
Git study and experiments

1. [Configuration (Global)](#configuration_global)
2. [Configuration (Local - Repository level)](#configuration_local)
3. [Delete](#delete_brances)
4. [Commit History](#commit_history)


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