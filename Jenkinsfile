pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy') {
            steps {
                sshagent(credentials: ['app-server-ssh']) {
                    sh '''
                      scp -o StrictHostKeyChecking=no index.html ubuntu@13.203.202.222:/var/www/html/index.html
                    '''
                }
            }
        }
    }
}
