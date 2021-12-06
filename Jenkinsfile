pipeline {
    agent any
    stages {
        stage("Pull Latest image"){
            steps{
                sh "docker pull prafast83/selenium-docker"
            }
        }
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