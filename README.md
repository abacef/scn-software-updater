# scn-software-updater

This is a series of ansible scripts to update various SCN servers. Currently it supports
- The **librenms** server's host OS packages and all of the service container's packages. (TODO: update the librenms software)
- The **app-backup** server's host OS (that is all that needs to be updated)
- The **rprox** server's host OS (TODO: update the docker compose file)

Since the idea is to create a dedicated server to run this on, we need to update that server too, so the script `update_self.sh` does that. You can add it to cron and it will update itself.


## Running an update script

Go into the ansible directory, create a venv and install the packages  in `requirements.txt`, then go into the desired folder name of the server you want to update and run `ansible-playbook -v -i inventory.ini playbook.yml`. Make sure to add the ssh key of the updater server to any server you are updating. 

You can set this up to run automatically by cloning this repo onto a update server and adding cron entries to run each update script like once per week or something. When someone changes the repo you can do a `git pull` and change the crontab accordingly

## Onboarding services
Create a directory in the `ansible` directory and write the backup script for your server. Note that ansible needs python to be installed on the target server's OS to run.
