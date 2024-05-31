pipeline {
    agent any
    stages {
        stage('Welcome') {
            steps {
                echo 'Hi, You are inside the pipeline'
            }
        }
        // stage('Checkout') {
        //     steps {
        //         git 'https://github.com/prabugann/jenkinspipeline.git'
        //     }
        // }
        stage('Build') {
            steps {
                echo 'skipping build'
            }
        }
        stage('Test') {
            steps {
                echo 'skipping test'
            }
        }
       stage('Install Nginx') {
            steps {
                script {
                    // Update package lists and install nginx
                    sh 'sudo -S apt-get update && sudo apt-get install -y nginx'
                }
            }
        }
        stage('Deploy Index.html') {
            steps {
                script {
                    // Copy index.html to the appropriate location
                    sh 'sudo -S cp index.html /var/www/html/'
                }
            }
        }
        stage('Restart Nginx') {
            steps {
                script {
                    // Restart nginx to apply changes
                    sh 'sudo -S systemctl restart nginx'
                }
            }
        }
    }
}