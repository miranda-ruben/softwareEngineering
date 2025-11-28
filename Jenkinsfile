pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling source code...'
                git url: 'https://github.com/miranda-ruben/softwareEngineering.git', branch: 'main'
            }
        }

        stage('Maven Build') {
            agent {
                docker { image 'maven:3.9.3-openjdk-17' } // Maven + JDK 17
            }
            steps {
                echo 'Running Maven build...'
                sh 'mvn clean compile test'
            }
        }

        stage('Gradle Build & Test') {
            agent {
                docker { image 'gradle:8.3-jdk17' } // Gradle + JDK 17
            }
            steps {
                echo 'Running Gradle build...'
                sh './gradlew build'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
