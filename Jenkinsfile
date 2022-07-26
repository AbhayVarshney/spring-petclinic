pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'java --version'
                sh './mvnw compile dependency:resolve'
                sh './mvnw dependency:resolve-plugins'
                sh './mvnw clean compile -DskipTests'
            }
        }
    }
}

