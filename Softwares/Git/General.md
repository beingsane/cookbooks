# General

## SSH key

Generate SSH key

	ssh-keygen -t rsa -C "email@domain.com"

Access home folder

	cd ~/.ssh/

Copy RSA key

	cat id_rsa.pub

## Fix Pull

git reset --hard HEAD
git clean -f -d
git pull
