pipeline {

   agent any

   stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh './mvnw package'
            }
        }

        stage('Scan') {
             steps {
                 withSonarQubeEnv(installationName: 'sq1') {
                     sh 'mvn clean install sonar:sonar'
                     sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                 }
             }
        }
    }
}

