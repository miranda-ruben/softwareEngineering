pipeline {
    agent any

    tools {
        maven 'Maven-3.9.3'
        gradle 'Gradle-8.3'
        jdk 'Java-17'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling source code...'
                checkout scm
            }
        }

        stage('Maven Build') {
    steps {
        withMaven(maven: 'Maven-3.9.3') {
            sh 'mvn clean compile'
        }
    }
}


        stage('Gradle Build & Test') {
            steps {
                echo 'Starting Gradle build...'
                sh 'gradle build --console=plain'
                sh 'gradle test --console=plain'
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
