# Ansible Virtual Environment Setup

This script can be used to setup a Python virtual environment for developing with Ansible. It installs Ansible Collections and Python modules within the virtual environment and then launches it.

## Prerequisites

- Software Packages: `python3, python3-pip, ansible`

## Procedure

1. Add the Ansible dependencies such as the `community.general, ansible.posix` collections in the `.env/ansible/requirements.yaml` file. The syntax for adding collections (local, remote, tar ball, git) is described [here](https://docs.ansible.com/ansible/latest/collections_guide/collections_installing.html#install-multiple-collections-with-a-requirements-file).

2. Add the Python dependencies such as the `ansible, jsonpath, kubernetes` modules in the `.env/ansible/requirements.txt` file. The syntax for adding pip packages is described [here](https://pip.pypa.io/en/stable/cli/pip_install/).

3. Launch the virtual environment
   ```sh
   . .env/launch.sh
   ```

4. Exit the virtual environment
   ```sh
   deactivate || (true && echo "Ansible Virtual Environment not active")
   ```
5. Refresh the virtual environment
   
   For example, environment reload as a result of new package or collection being added in the `requirement.{txt,yaml}` file.
   ```sh
   deactivate || (true && echo "Ansible Virtual Environment not active")
   rm -rf .ansible-venv
   . .env/launch.sh
   ```

