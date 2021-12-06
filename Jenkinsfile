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
    }
    post {
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }
}