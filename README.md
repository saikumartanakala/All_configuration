# ubuntu
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
