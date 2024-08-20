# ubuntu

# steps to setup docker
#Run the following command to uninstall all conflicting packages:
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

#Install using the apt repository
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

#Install the Docker packages.
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

#Verify that the Docker Engine installation is successful by running the hello-world image.
sudo docker run hello-world

systemctl start docker or
systemctl enable --now  docker
systemctl status docker
docker images (to show the all images)
docker ps -a (to show running containers)
docker build -t imagesname .
docker run -d -p 8080:8080 running_image_name

df -a (to show the disk space)






# step to install jenkins in ubuntu server
sudo apt-get update
java -version

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

sudo systemctl start jenkins.service
sudo systemctl status jenkins
ufw allow 8080
sudo ufw enable
enter yes
sudo ufw status


in server allow  security group 8080 port 
cat /var/lib/jenkins/secrets/initialAdminPassword
copy the code and paste in Jenkins server
installation process takes time
username
password
confirm password
full name
gmail
click save and continue

############################################################################################################################################
# ubuntu

# steps to setup docker
#Run the following command to uninstall all conflicting packages:
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

#Install using the apt repository
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

#Install the Docker packages.
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

#Verify that the Docker Engine installation is successful by running the hello-world image.
sudo docker run hello-world

systemctl start docker or
systemctl enable --now  docker
systemctl status docker
docker images (to show the all images)
docker ps -a (to show running containers)
docker build -t imagesname .
docker run -d -p 8080:8080 running_image_name

df -a (to show the disk space)






# step to install jenkins in ubuntu server
sudo apt-get update

sudo apt update
sudo apt install openjdk-17-jdk

java -version

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

sudo systemctl start jenkins.service
sudo systemctl status jenkins
ufw allow 8080
sudo ufw enable
enter yes
sudo ufw status


in server allow  security group 8080 port 
cat /var/lib/jenkins/secrets/initialAdminPassword
copy the code and paste in Jenkins server
installation process takes time
username
password
confirm password
full name
gmail
click save and continue



error

sudo apt-get update

sudo apt-get install default-jdk



STEPS TO INSTALL JENKINS NEW

1.sudo apt-get update
sudo apt-get upgrade
2.sudo apt-get install openjdk-11-jdk -y
3.java -version
4.curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
5.echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
6.sudo apt-get update
sudo apt-get install jenkins -y
7.sudo systemctl start jenkins
sudo systemctl enable jenkins
8.sudo ufw allow 8080
sudo ufw status
9.http://your_server_ip_or_domain:8080
10.


DELETE THE ALL FILE OF JENKINS AT ERROR OCCUR

1.sudo systemctl stop jenkins
2.sudo apt-get remove --purge jenkins
3.sudo rm -rf /var/lib/jenkins
4.sudo rm -rf /var/log/jenkins
5.sudo rm -rf /etc/default/jenkins
sudo rm -rf /etc/init.d/jenkins
6.sudo deluser jenkins
7.sudo apt-get autoremove
8.ls /var/lib/jenkins
ls /var/log/jenkins
9.



