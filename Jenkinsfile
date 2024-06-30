pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/newbie7ht/node-js-basic.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    docker.build('my-app:latest')
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Example test step
                    sh 'echo "Running tests..."'
                }
            }
        }
        stage('Deploy') {
            steps {
                ansiblePlaybook credentialsId: 'your-ansible-credentials-id', playbook: 'deploy.yml'
            }
        }
    }
}
