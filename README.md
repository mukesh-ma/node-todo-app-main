This Java application serves as a basic example to demonstrate the integration of Jenkins with Git webhooks.

Steps followed on high level:

    Launch EC2 Instance: Deploy an Ubuntu-based EC2 instance on AWS.
    Install Dependencies: Install Docker, Docker Compose, Java, and Jenkins on the instance.
    Jenkins Setup: Configure Jenkins (e.g., unlock, install plugins, set up user, etc.).
    GitHub Webhook: Set up a webhook on the Git project to notify Jenkins on changes.
    Trigger Build: Make a Git commit to automatically trigger a Jenkins build via the webhook.

Deploy an EC2 instance of Ubuntu on AWS:
Refer to ‘https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/gs-ubuntu.html‘

Following commands on the Ubuntu terminal needs to be executed:

*Upgrade Ubuntu apt-get:
sudo apt-get update
sudo apt-get upgrade

*Install docker:
sudo apt-get install docker.io

*Install docker-compose:
sudo apt-get install docker-compose

*Install Java:
sudo apt install openjdk-17-jdk-headless

*Install Jenkins:
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo “deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]”
https://pkg.jenkins.io/debian-stable binary/ | sudo tee
/etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

*Verify Jenkins install:
systemctl status jenkins

*Grant access to docker:
sudo usermod -aG docker $USER
sudo usermod -aG docker jenkins

*Jenkins configuration:
Refer to ‘https://www.jenkins.io/doc/book/installing/linux/‘

*Webhooks configuration:
Refer to ‘https://docs.github.com/en/webhooks/using-webhooks/creating-webhooks‘

*NOTES:

Open ports 8000 (for the to do application) and 8080 (for Jenkins) on the EC2 Ubuntu instance.
