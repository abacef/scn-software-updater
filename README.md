# scn-software-updater

As of now, you can update the OS software packages on the librenms server, including the OS packages on all docker containers currently running. This may in the future update the actual applications running in those containers too. To run this, go into the ansible directory, create a venv and install the packages  in `requirements.txt`, then go into the librenms directory and run `ansible-playbook -v -i inventory.ini playbook.yml`

Since the idea is to create a dedicated server to run this on, we need to update that server too, so the script `update_self.sh` does that. You can add it to cron and it will update itself.
