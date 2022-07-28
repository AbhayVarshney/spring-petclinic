pipeline {

   agent any

   stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh './mvnw package sonar:sonar -DskipTests'
            }
        }

        stage('Scan') {
             steps {
                 withSonarQubeEnv(installationName: 'sq1') {
                      sh './mvnw clean install sonar:sonar -DskipTests -Dsonar.login'                     
                 }
             }
        }
    }
}

