pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                checkout scm 
            }   

        }

        stage('Build image') {
            steps {
                app = docker.build('afangndong/beautygit config advice.addEmptyPathspec false')
            }
        }

        stage('Push image') {
            steps { 
                docker.withRegistry('https://registry.hub.docker', 'docker-hub-credentials') {
                     app.push("${env.BUILD_NUMBER}")
                     app.push("latest")
                }
            }
        }

    }
}
