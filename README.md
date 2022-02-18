# ansible-wordpress
A repo for creating WordPress site with Ansible. This repo targets Oracle Linux 8 on OCI on ARM64 processor. Most of the Ansible code in this repo will work for Oracle Linux 8 on AMD and Intel processors but you may need to tweak some things in this repo. ARM64 is faster and more reasonable anyway, so I chose this to be the starting point.


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

## Edit vars.yaml file
Determine your passwords and database name for your WordPress site in vars.yaml file. 

## Place your SSL cert
Place your SSL cert under files directory and modify vars.yaml to match the file names of .key and .crt files.

## List Host
You can alternatively execute the following command to list the host.
```
ansible-playbook main.yaml --list-host
```

## Dry Run
You can dry run the Ansible playbook
```
ansible-playbook main.yaml --check
```
Some steps may fail because dry run doesn't actually upload necessary files.

## Run Configuration
To actually make changes to the target host, execute the following command.
```
ansible-playbook main.yaml
```