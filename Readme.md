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
    ansible-playbook -i your_inventory_file main.yml
    ```

4. Access NGINX:

   - EC2: http://your-ec2-ip/
   - Docker Container: http://your-ec2-ip:8001/

## Directory Structure

- `roles/nginx`: Ansible role directory.
  - `defaults`: Default variables for the role.
  - `files`: Static files (e.g., NGINX configuration files).
  - `handlers`: Handlers for the role.
  - `meta`: Metadata for the role (e.g., role dependencies).
  - `tasks`: Main tasks for the role.
    - `main.yml`: Tasks for installing and configuring NGINX.
  - `templates`: Template files used by the role.
  - `vars`: Variables for the role.
- `main.yml`: Main playbook to orchestrate tasks.
- `your_inventory_file`: Ansible inventory file.

## Customization

You can customize the playbook and the `nginx` role according to your specific requirements:

- Adjust ports and configurations in `main.yml`.
- Modify NGINX configurations in `roles/nginx/files` and `roles/nginx/templates`.

## Contributing

Feel free to contribute by opening issues, providing feedback, or submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
