## Submodules

	touch .gitmodules

Add submodule

	git submodule add repo_url path/to/module

Remove folder/module from git repository

	git rm -r --cached path/of/module

Update from submodule folder

	cd path/of/module
	git pull

Update all submodules

	git submodule foreach git pull

or

	git submodule foreach git pull origin master

Close with submodules

	git clone --recursive repo_url

Get submodules from cloned repo

	git submodule update --init --recursive
