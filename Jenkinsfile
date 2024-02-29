pipeline {
    agent any

    stages {
        stage('Install httpd') {
            steps {
                sh '''
                sudo apt-get update
                sudo apt-get install -y apache2
                '''
            }
        }

        stage('Check logs for errors') {
            steps {
                sh '''
                sudo cat /var/log/apache2/access.log | grep -E 'HTTP/1.1\" [4-5][0-9][0-9]'
                '''
            }
        }
    }
}
