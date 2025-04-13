pipeline {
    agent {
        label 'agent-with-ssh'
    }
    environment {
        workspace = "/home/sharthu/project/flask_jekins01"
    }
    stages {
        stage('Checkout Source') {
            steps {
                ws("${workspace}") {
                    checkout scm
                }
            }
        }
        stage('Docker Comopse Build') {
            steps {
                ws("${workspace}"){
                    sh "docker compose build --no-cache frontend backend"
                }
            }
        }
        stage('Docker Comopse Up') {
            steps {
                ws("${workspace}"){
                    sh "docker compose up --no-deps -d frontend backend"
                }
            }
        }
    }
}