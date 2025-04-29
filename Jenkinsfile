pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                if (isUnix()) {
                    sh 'echo "Build completed"'
                } else {
                    bat 'echo "Build completed"'
                }
            }
        }
    }
}

