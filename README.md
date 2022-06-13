# Configuration Management - Ansible - Node JS with PM2 Web Server deployment and Configuration of Remote EC2

This Ansible playbook installs Nodejs and NPM dependencies on an Amazon Linux EC2

The Inventory File contains the IP addresses curl with the command below. The EC2 should have tags name Project with Value udacity

aws ec2 describe-instances         --query 'Reservations[*].Instances[*].PublicIpAddress'       --filters "Name=tag:Project,Values=udacity"       --output text >> inventory

The Playbook has a role called setup which installs and configures the web server

The playbook is run with the command below

ansible-playbook main-remote.yml -i inventory --private-key EC2KeyPair