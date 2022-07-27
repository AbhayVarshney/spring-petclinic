pipeline {

   agent any

   stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh './mvnw package -DskipTests'
            }
        }

        stage('Scan') {
             steps {
                 withSonarQubeEnv(installationName: 'sq1') {
                     sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar -DskipTests'
                 }
             }
        }
    }
}

