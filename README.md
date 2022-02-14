# ansible-wordpress
A repo for creating WordPress site with Ansible


## Clone this repo.
1. Open terminal.
1. Navigate to a directory where you want to clone this repo.
1. Clone this repo.
    ```
    git clone git@github.com:hiriumi/ansible-wordpress.git
    ```
## Install Ansible
We'll install Ansible before we can use it. Please follow the steps below.
1. Install Python virtual environment.
    ```
    python3 -m venv venv
    ```
1. Activate it.
    ```
    source ./venv/bin/activate
    ```
1. Install Ansible.
    ```
    pip install ansible
    ```
Now you are ready to execute Ansible!

## Edit hosts File
This repo has **hosts** file that has **target_host** group. You can specify the FQDN or IP address of the target host you want to configure. You can specify multiple hosts in the **target_host** group.
## Dry run main.yaml
Before you actually make the changes on the specified host in ansible-wordpress/hosts file, you can check if it's going to target the host you intend to.
```
ansible-playbook main.yaml --check
```
## List Host
You can alternatively execute the following command to list the host.
```
ansible-playbook main.yaml --list-host
```

## Execute
