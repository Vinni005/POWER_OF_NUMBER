pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning...'
                git branch: 'main', url: 'https://github.com/Vinni005/POWER_OF_NUMBER.git'
            }
        }
        stage('Update the packages') {
            steps {
                sh 'yum update httpd -y'
            }
        }

        stage('Start httpd') {
            steps {
                sh 'systemctl start httpd'
            }
        }

        stage('Clean the Root folder') {
            steps {
                sh 'rm -r /var/www/html/'
            }
        }

        stage('Copy file') {
            steps {
                sh 'cp -r /var/lib/jenkins/workspace/${env.JOB_NAME}/* /var/www/html/'
            }
        }
    }
}
