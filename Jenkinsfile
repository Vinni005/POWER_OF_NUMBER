pipeline {
    agent any
    stages{
        stage('Checkout'){
			steps {
                 git 'https://github.com/akshu20791/DevOpsClassCodes.git'
            }
        }

    stages {
        stage('Update the packages') {
            steps {
                sh 'sudo yum update httpd -y'
            }
        }

        stage('Start httpd') {
            steps {
                sh 'sudo systemctl start httpd'
            }
        }

        stage('Clean the Root folder') {
            steps {
                sh 'sudo rm -r /var/www/html/'
            }
        }

        stage('Copy file') {
            steps {
                sh 'sudo cp -r /var/lib/jenkins/workspace/${env.JOB_NAME}/* /var/www/html/'
            }
        }
    }
}