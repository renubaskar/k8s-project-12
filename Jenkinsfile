pipeline {
    agent any
    stages {
        stage('Pull Code From GitHub repo') {
            steps {
                git 'https://github.com/renubaskar/k8s-project-12.git'
            }
        }
        stage('Build the Docker image') {
            steps {
                sh 'sudo docker build -t k8simage /var/lib/jenkins/workspace/k8s-project-12'
                sh 'sudo docker tag k8simage renubaskar7/k8simage:latest'
                sh 'sudo docker tag k8simage renubaskar7/k8simage:${BUILD_NUMBER}'
            }
        }
        stage('Push the Docker image') {
            steps {
                sh 'sudo docker image push renubaskar7/k8simage:latest'
                sh 'sudo docker image push renubaskar7/k8simage:${BUILD_NUMBER}'
            }
        }
    }
}
