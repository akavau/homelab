# Homelab
In this project I will document the setup of my homeserver which will be used for several data engineering projects.

## ansible

Execute command
	# Execute playbook
	$ ansible-playbook -i IP-Adress, -u USER -k -K ansible/playbooks/configure.yml

Explanation
	# -i IP_ADRESS,
	This is an inline inventory and can be used instead of an inventory.yml file.
	The comma at the end is important!

	# -u USER
	This defines the user, that is used to login to the home server.
	This can be any existing user or the one created with the Kickstart file.

	# -k -K
	The "-k" asks for the SSH password, the "-K" requests the sudo passwords.
	In general it is the same and ansible is aware of this, as you can see in the prompt when executing.

Installing collections
	# Install collections from the requirements.yml
	$ ansible-galaxy collection install -r ansible/requirements.yml

## Running the ansbile-playbook

	# Syntax Check the playbook - to look for syntax errors without executing the playbook
	$ ansible-playbook --syntax-check ansible/playbooks/configure.yml

	# Dry-Run the playbook - to check what will be changed
	$ ansible-playbook -i IP_ADDRESS, -u USER -k -K --check ansible/playbooks/configure.yml

	# Run the playbook - to really do the work
	$ ansible-playbook -i IP_ADSRESS, -u USER -k -K ansible/playbooks/configure.yml
