ansible-playbook -i demo-server config.yml -K

nano /etc/apt/sources.list.d/docker.list
sudo rm /etc/apt/sources.list.d/docker.list


sudo apt install ansible-lint
ansible-lint config.yml 

sudo apt install pre-commit
pre-commit --version
pre-commit install


