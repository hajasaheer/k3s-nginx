pipeline {
    agent any

    environment {
        MASTER_IP = '192.168.56.101'
        SSH_USER = 'vagrant'
        SSH_KEY = '~/.vagrant.d/insecure_private_key'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR-USERNAME/my-nginx-app.git'
            }
        }

        stage('Deploy to K3s') {
            steps {
                sh '''
                scp -i $SSH_KEY -o StrictHostKeyChecking=no nginx-hello.yml $SSH_USER@$MASTER_IP:/home/vagrant/
                ssh -i $SSH_KEY -o StrictHostKeyChecking=no $SSH_USER@$MASTER_IP \
                  "kubectl apply -f /home/vagrant/nginx-hello.yml"
                '''
            }
        }
    }
}
