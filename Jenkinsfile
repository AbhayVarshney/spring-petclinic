pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'get java version'
                sh 'java --version'
                sh './mvnw clean compile'
            }
        }
    }
}

