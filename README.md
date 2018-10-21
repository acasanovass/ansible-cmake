# ansible-cmake
Ansible playbooks to install cmake component un Windows, Linux and MacOS

HOW TO RUN IT
Run it in the controller by using: ansible-playbook main.yaml -i inventory.txt --extra-vars "ansible_sudo_pass=1234" -v
*** Remember to adjust the inventory so you are sure on which server or groups you are running it!

PRE REQUISITES AND ASSUMPTIONS
All:
 - Users named admin exist and the password is 1234
 - The Linux machine with the Ansible controller is able to see all the others
 - For this exercise plan passwords have been used instead of keys via Vault
 - There is a main playbook that have them all, but modify the inventory with the hosts where you want to try this and just comment out the playbooks that you don't want to use if any

Windows:
 - The ansible controller has winrm installed. If not, run the following: pip install "pywinrm>=0.2.2"
 - Winrm is enabled is able on windows. If it's not, reffer to this guide: https://www.ansible.com/blog/connecting-to-a-windows-host

Linux (Ubuntu):
 - Python 2x is installed. If it's not -> sudo apt-get -y install python
 - Ensure that the user you are using, has been added to the sudoers, if not can be done like this: "sudo usermod -aG sudo $username"

MacOS:
 - The XCode Command Line Tools are installed. If they are not, just run gcc in a terminal and install them with the popup.
 - Homebrew has been installed previously to manage packages. If not, execute this:  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
