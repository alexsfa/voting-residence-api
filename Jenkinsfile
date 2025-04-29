pipeline {
    agent any

    environment {
        PROJECT_NAME = 'vote_residence'
        IMAGE_NAME = 'voting_residence_api'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/alexsfa/voting-residence-api.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}")
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    docker.image("${IMAGE_NAME}").inside {
                        sh 'python manage.py test' // or use pytest
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
        }
        success {
            echo 'CI passed successfully!'
        }
        failure {
            echo 'CI failed. Check the logs.'
        }
    }
}