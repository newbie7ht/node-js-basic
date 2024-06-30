pipeline {
    agent any
    environment {
        KUBECONFIG = '/var/jenkins_home/.kube/config'  // Path to the Kubernetes config file
    }
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
        stage('Deploy to Kubernetes') {
            steps {
                container('kubectl') {
                    sh "kubectl apply -f deploy.yml"  // Replace with your deployment command
                }
            }
        }
    }
}
