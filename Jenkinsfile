pipeline {
    agent{
        label 'openjdk-11'
    }

    stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh './mvnw package'
            }
        }
    }
}

