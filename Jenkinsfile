pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'my-lap-git',
                    url: 'https://github.com/sukanya74/devops_lab-'
            }
        }

        stage('Deploy') {
            steps {
                sshagent('appserver-key') {
                    sh '''
                    scp ci-cd-task/index.html ubuntu@13.127.131.210:/var/www/html/index.html
                    '''
                }
            }
        }
    }
}
