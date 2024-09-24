pipeline {
    agent any
    def app
    stages {
        stage('Git Checkout') {
            steps {
                checkout scm 
            }   

        }

        stage('Build image') {
            steps {
                app = docker.build('afangndong/beauty.git')
            }
        }

        stage('Push image') {
            steps { 
                docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                     app.push("${env.BUILD_NUMBER}")
                     app.push("latest")
                }
            }
        }

    }
}
