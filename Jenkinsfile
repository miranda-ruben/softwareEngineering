pipeline {
    agent any

    tools {
        maven 'Maven'      // Make sure Jenkins has a Maven installation configured
        jdk 'Java 17'      // Make sure Jenkins has JDK installed
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building project with Maven...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging project...'
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs!'
        }
    }
}
