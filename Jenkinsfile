pipeline {
agent any

```
tools {
    maven 'Maven-3.9.6'   
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

    stage('Maven Build & Test') {
        steps {
            echo 'Starting Maven build...'
            sh 'mvn clean compile'
            sh 'mvn test'
            echo 'Maven build and tests completed'
        }
    }

    stage('Gradle Build & Test') {
        steps {
            echo 'Starting Gradle build...'
            sh 'gradle build --console=plain'
            sh 'gradle test --console=plain'
            echo 'Gradle build and tests completed'
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
```

}
