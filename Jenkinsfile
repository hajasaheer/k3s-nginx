pipeline {
agent any
environment {
MASTER_IP = '192.168.56.101'
}
stages {
stage('Checkout') {
steps {
git url: 'git@github.com:hajasaheer/k3s-nginx.git'
}
}
stage('Deploy to K3s') {
steps {
sshagent (credentials: ['vagrant-key']) {
sh """
scp -o StrictHostKeyChecking=no nginx-hello.yml
vagrant@$MASTER_IP:/home/vagrant/
ssh -o StrictHostKeyChecking=no vagrant@$MASTER_IP "sudo kubectl
apply -f /home/vagrant/nginx-hello.yml"
"""
}
}
}
}
}
