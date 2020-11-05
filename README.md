# centos-jenkins-container
This example will use an Ansible playbook to automatically install SSMTP in the Jenkins container to enable the mail service and allow the SSL access to Jenkins server.

# System
- Linux Centos 7.5 / 7.6
- AWS, Azure, Linode or GCP Cloud
- Docker container: jenkins-2-centos7
- Jenkins Server

# IaC
- Ansible playbook
- Dockerfile

# PACKAGES
- docker-client
- epel-release
- ansible
- python-pip
- net-tools 
- iproute 
- ssmtp
- pip
- pyopenssl
- apache-libcloud
- cryptography
- ansible[azure]

# NOTE
- install keytool to generate the keystore: yum install java-1.8.0-openjdk
- create directory /opt/jenkins/ if not exists
- create keystore with password 'password123' or update Dockerfile to your own password setting
- keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
- move my-release-key.keystore to /opt/jenkins/my-release-key.keystore

# INSTALLATION
ansible-playbook -i host playbook.yml

