## Jenkins and Docker Installation Playbook for Ubuntu

This Ansible playbook automates the installation and setup of both **Jenkins** and **Docker** on an Ubuntu machine. It is designed to be executed on any Ubuntu-based system, and it covers tasks such as installing necessary dependencies, adding Jenkins' official repository, setting up Docker, and starting the Jenkins and Docker services.

## Prerequisites

Before running this playbook, make sure you have the following:

- **Ansible** installed on your local machine.
- **Root or sudo privileges** on the remote Ubuntu server.
- **SSH access** to the target machine.

## Usage

1. **Clone this repository**:
    ```bash
    git clone https://github.com/SupriyaKarnati/Ansible-Projects.git
    cd jenkins-installation
    ```

2. **Modify your `hosts` file**:  
   In the same directory as the playbook, modify the `hosts` file to include the IP addresses or hostnames of the Ubuntu machines where Jenkins should be installed. The file should look something like this:
    ```ini
    [ubuntu_servers]
    192.168.1.100
    ```

3. **Run the Ansible Playbook**:
    Ensure that you are running Ansible with appropriate privileges to perform system modifications on the target machine. Use the following command to run the playbook:

    ```bash
    ansible-playbook -i hosts main.yml
    ```

   The `-i hosts` flag specifies the inventory file containing the target machines' details.

4. **Access Jenkins**:
   Once the playbook has completed successfully, Jenkins should be installed and running. Open your browser and visit the Jenkins server at the following URL:

    ```
    http://<your_ubuntu_server_ip>:8080
    ```

   The first time you access Jenkins, you will be prompted to unlock Jenkins. You can find the unlock key by running the following command on the server:

    ```bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```

   Copy the password and paste it into the unlock prompt to finish the setup.

5. **Access Docker**:
   After Docker is installed, you can check its status by running:

    ```bash
    sudo systemctl status docker
    ```

   To verify Docker is running, you can also execute:

    ```bash
    sudo docker --version
    ```
    
## Playbook Details

This playbook automates the following tasks:

- **Update the system**: Ensures that the system packages are up to date.
- **Install necessary dependencies**: Installs Java (as Jenkins requires Java to run) and other prerequisites.
- **Add Jenkins' official repository**: Ensures Jenkins' repository is added and the system is configured to install the latest stable version.
- **Install Jenkins**: Installs Jenkins via the official repository.
- **Install Docker**: Installs Docker CE (Community Edition) and sets it up for the user.
- **Start Jenkins service**: Starts the Jenkins service and enables it to start on boot.
- **Open port 8080**: Ensures the firewall allows traffic on port 8080 (the default Jenkins port).
