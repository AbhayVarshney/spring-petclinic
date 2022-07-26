pipeline {
    agent{
        label 'openjdk-11'
    }

    stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh './mvnw compile dependency:resolve'
                sh './mvnw dependency:resolve-plugins'
                sh './mvnw clean compile -DskipTests'
            }
        }
    }
}

