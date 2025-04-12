Deploy an EC2 instance of Ubuntu on AWS
Refer to ‘https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/gs-ubuntu.html‘

Following commands on the Ubuntu terminal needs to be executed:
Upgrade Ubuntu apt-get

sudo apt-get update
sudo apt-get upgrade
Install docker

sudo apt-get install docker.io
Install docker-compose

sudo apt-get install docker-compose
Install Jave (pre-requisite for Jenkins)

sudo apt install openjdk-17-jdk-headless
Install Jenkins

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo “deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]” \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
Verify Jenkins install

systemctl status jenkins
Grant access to docker

sudo usermod -aG docker $USER
sudo usermod -aG docker jenkins

*Jenkins configuration
Refer to ‘https://www.jenkins.io/doc/book/installing/linux/‘

*Webhooks configuration
Refer to ‘https://docs.github.com/en/webhooks/using-webhooks/creating-webhooks‘

*NOTES:

    Open ports 8000 (for the to do application) and 8080 (for the Jenkins) on the EC2 Ubuntu instance
