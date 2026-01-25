pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/sukanya74/devops_lab.git'
            }
        }

        stage('Deploy') {
            steps {
             sshagent(['appserver-key']) {
    sh '''
    scp -o StrictHostKeyChecking=no index.html ubuntu@13.127.131.210:/var/www/html/
    '''
}
            }
        }
    }
}
