# This is my FYP CI/CD tool

This is a tool to deploy the latest source code to my local server when there is new version on a specific branch.

# Logic

The restart procedules are $docker-compose down and $docker-compose up
# Prerequisites 
  1. Install Ansible
  2. Install Cron Jobs: https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/ch-automating_system_tasks
 
# How to use?
  1.  Please edit the source code path in ./group_vars/all.yml file. E.G. source_code_path: ~/RIC-1-Backend/
  2.  ansible-playbook main.yml
  3.  Add the cron to /etc/crontab when you are using root account
  `*  *  *  *  * root ansible-playbook /root/fyp-cicd/main.yml  >> /var/log/fyp-ansible.log 2>&1`
