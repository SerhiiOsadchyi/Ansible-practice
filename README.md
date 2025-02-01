ansible-playbook -i demo-server config.yml -K

nano /etc/apt/sources.list.d/docker.list
sudo rm /etc/apt/sources.list.d/docker.list

ansible-galaxy collection install community.docker --force 

sudo apt install ansible-lint
ansible-lint config.yml 

** ansible-app with nginx  **

ansible-playbook -i inventory all.yml --tags "preconfig"

ansible-playbook -i inventory all.yml --tags "build"
sudo nano /etc/hosts    //  on my comp => add line = 127.0.0.1 image.local


docker run -d -p 5000:5000 --name local-registry registry:2
http://localhost:5000/

ansible-playbook -i inventory all.yml --tags "deploy"

ansible-playbook -i inventory all.yml --tags "swarm_init, swarm_join"

pre-commit run --all-files
sudo rm -rf .git/hooks/pre-commit