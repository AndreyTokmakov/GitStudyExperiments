# GitStudyExperiments
Git study and experiments


###  Configuration (Global)

View global configuration:

	git config --global -l	


Ensure your commits are tagged with the correct identity.

	git config --global user.name "Your Name"
	git config --global user.email "username@gmail.com"

Unset (global): (delete global 'user.name' and 'user.email' parameters)

    git config --global --unset user.name
    git config --global --unset user.email


###  Configuration (Local - Repository level)

View configuration:

	git config -l

Set 'name' and 'email'

    git config user.name "Your Name"
    git config user.email "username@gmail.com"


###  Delete brances:

    git branch -D some_network_waiting_utilities                     #  Delete a local branch
    git push origin --delete some_network_waiting_utilities          #  Remove a remote branch 