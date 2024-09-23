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

########################################################################################################################


PROMETHEOUS WORKING FLOW

1.go to google search
prometheous download
sudo apt update
sudo apt upgrade -y
sudo useradd --no-create-home --shell /bin/false prometheus
sudo mkdir /etc/prometheus
sudo mkdir /var/lib/prometheus
wget https://github.com/prometheus/prometheus/releases/download/v2.49.0/prometheus-2.49.0.linux-amd64.tar.gz
tar xvf prometheus-*.tar.gz
cd promenteous file
sudo mv prometheus promtool /usr/local/bin/
sudo mv consoles/ console_libraries/ /etc/prometheus/
sudo mv prometheus.yml /etc/prometheus/
sudo chown -R prometheus:prometheus /etc/prometheus
sudo chown -R prometheus:prometheus /var/lib/prometheus
sudo chown prometheus:prometheus /usr/local/bin/prometheus
sudo chown prometheus:prometheus /usr/local/bin/promtool
CREATE FILE
sudo nano /etc/systemd/system/prometheus.service


FILE 
[Unit]
Description=Prometheus
Wants=network-online.target
After=network-online.target

[Service]
User=prometheus
Group=prometheus
Type=simple
ExecStart=/usr/local/bin/prometheus \
    --config.file /etc/prometheus/prometheus.yml \
    --storage.tsdb.path /var/lib/prometheus/ \
    --web.console.templates=/etc/prometheus/consoles \
    --web.console.libraries=/etc/prometheus/console_libraries

[Install]
WantedBy=multi-user.target

ctrl + x
y
edit file name
enter

sudo systemctl daemon-reload
sudo systemctl start prometheus
sudo systemctl enable prometheus

sudo systemctl status prometheus

Prometheus allow port is 9090

""STORAGE CHECK COMMANDS""

1.Check Disk Usage by Directory-->du -h --max-depth=1 | sort -h
du stands for disk usage.
-h makes the output human-readable (e.g., KB, MB, GB).
--max-depth=1 restricts the depth to show only the top-level directories.
sort -h sorts the output by size, with the largest directories at the bottom.
2.Find Largest Directories and Files----->sudo du -ah / | sort -rh | head -n 20
-a includes both files and directories.
-r sorts in reverse order, showing the largest first.
head -n 20 limits the output to the top 20 largest entries.
3.Check a Specific Directory------>du -h /home --max-depth=1 | sort -h
4.Check Disk Usage for Root Directory----->sudo du -xh / | sort -h | tail -n 20
-x stays within the filesystem (e.g., avoids crossing into mounted filesystems).
tail -n 20 shows the largest 20 files or directories at the bottom.
5.Using ncdu for Interactive Disk Usage---->sudo apt update
                                      ----->>sudo apt install ncdu
                                 ----------->ncdu /
                                 close the window--->ctrl + z
6.Clear Specific Application Caches--->sudo apt-get clean
                                   ---->rm -rf ~/.cache/thumbnails/*
7.Filesystem      Size  Used Avail Use% Mounted on---->df -h
8.all files storage ----->df -ah or df -all or df -al 
9.to show storage and file names  only used space---> du -h
10.to show storage and file names  all space---> du -a






@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

PROMETHEOUS SETUP
1.go to google search promethous download
2.select linux 
3.copy the link
4.wget paste the link
5. tar -zxvf paste the link
6.after the extraction of file
7.cd to that file
8.rum the promenthous server
9.how to start the server ./Prometheus
10.sudo lsof -i :9090(check the whiich port is allocated )
11.check the promethous is running are not(http://3.108.40.205:9090/)
12.search the required metrics and execute

INSTALL NODE_EXPORTER
1.1.go to google search promethous download
2.select linux 
3.copy the link
4.wget paste the link
5. tar -zxvf paste the link
6.after the extraction of file
7.cd to that file
8.run node_exporter
9../node_exporter
10.how to stop the node_exporter --->ctrl + c
11.after that refresh the all items(Prometheus server,node server, promenthous browser, node_exporter bowser)
12.node_exporter bowser is stop then we need to start again
13.at this time the node_exporter is stops so we need to write the service file
14.cd /etc/systemd/system/
15. vi node_exporter.service
16.
[Unit]
Description=Node Exporter
Requires=node_exporter.socket

[Service]
EnvironmentFile=/etc/sysconfig/node_exporter
ExecStart=/root/node/node_exporter --web.systemd-socket $OPTIONS

[Install]
WantedBy=multi-user.target
17.cd
18.cd node file
19.systemctl daemon-reload
