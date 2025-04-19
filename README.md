# Update Services Role

 Ansible role updates and installs Docker and Ollama on the localhost machine.
 The deploy starts and sets up the services

## Prerequisites

* Ansible installed on your control machine.
* SSH access is not required, as the playbook runs locally.

## Running the Playbook

Navigate to the directory containing your playbook (e.g., `ansible_project/`) and run the following command:

```bash
ansible-playbook ai-deploy-playbook.yml -c local -i inventory.yml

1. Run a Single Tag:

To run tasks associated with a single tag, use the --tags option followed by the tag name:

ansible-playbook ai-deploy-playbook.yml -c local --tags docker-update #just to update docker

ansible-playbook ai-deploy-playbook.yml -c local --tags docker-install,docker-update #to install and update docker only

ansible-playbook ai-deploy-playbook.yml -c local --tags update-all #updates everything

ansible-playbook ai-deploy-playbook.yml -c local --tags docker-install,ollama-update

If you want to run the playbook and exclude certain tags, use the --skip-tags option:
ansible-playbook ai-deploy-playbook.yml -c local --skip-tags ollama-install

Available Tags
You can use tags to selectively run tasks within the role. Here's a list of the available tags:

ubuntu: Updates Ubuntu packages.
docker-install: Installs Docker if not already present.
docker-update: Updates Docker if it's already installed.
ollama-install: Installs Ollama if not already present.
ollama-update: Updates Ollama if it's already installed.
check-updates: Checks for available updates for Docker and Ollama without performing the update.
update-all: Runs all tasks in the role (installs if needed, then updates).