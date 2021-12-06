pipeline {
    agent any
    stages {
        stage("Start Grid") {
            steps{
                sh "docker-compose up -d selenium-hub chrome firefox"
            }
        }
        stage("Run Test"){
            steps{
                sh "docker-compose up selenium-docker"
            }
        }
        stage("Stop Grid"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}