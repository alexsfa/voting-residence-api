pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script { 
                    if (isUnix()) {
                        sh 'echo "Build completed"'
                    } else {
                        bat 'echo "Build completed"'
                    }
                }
            }
        }
    }
}

