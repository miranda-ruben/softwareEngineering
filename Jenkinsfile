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
                git url: 'https://github.com/miranda-ruben/softwareEngineering.git', branch: 'main'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn clean compile test'
            }
        }

        stage('Gradle Build & Test') {
            steps {
                sh './gradlew build'
            }
        }
    }

    post {
        success { echo 'Pipeline completed successfully!' }
        failure { echo 'Pipeline failed!' }
    }
}
