pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling source code...'
            }
        }

        stage('Build') {
            steps {
                echo 'Simulating build step...'
                sh 'echo "Compiling source..."'
                sh 'sleep 2'
                sh 'echo "Build completed!"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "All tests passed!"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
