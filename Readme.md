# Ansible NGINX Role

This Ansible role automates the installation and configuration of NGINX on both an EC2 instance and a Docker container. It performs the following tasks:

1. Installs NGINX on an EC2 instance.
2. Creates an Ubuntu-based Docker container.
3. Installs and configures NGINX inside the Docker container.
4. Maps ports to make NGINX accessible on designated ports.

## Prerequisites

- Ansible installed on your local machine(In my case I used an ec2 instance and installed Ansible on it).
- AWS credentials configured for the EC2 instance.
- Docker installed on the target machine.

## Usage

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/ansible-nginx-role.git
    ```

2. Update the Ansible playbook with your specific details.

3. Run the playbook:

    ```bash
     ansible-playbook -i inventory --tags docker playbook.yml -vvv
     ansible-playbook -i inventory --tags ec2 playbook.yml -vvv
    ```

4. Access NGINX:

   - EC2: http://your-ec2-ip/
   - Docker Container: http://your-ec2-ip:8001/

## Directory Structure

- `roles/nginx`: Ansible role directory.
  - `defaults`: Default variables for the role.
  - `handlers`: Handlers for the role.
  - `tasks`: Main tasks for the role.
    - `ec2.yml`: Tasks for installing and configuring NGINX on ec2.
    - `docker.yml`: Tasks for installing and configuring NGINX on the docker container.
    - `main.yml`: Tasks for installing and configuring NGINX on docker and ec2 based on tags
  - `vars`: Variables for the role.
- `playbook.yml`: Main playbook to orchestrate tasks.
- `your_inventory_file`: Ansible inventory file for mapping ec2 IP or hostname

