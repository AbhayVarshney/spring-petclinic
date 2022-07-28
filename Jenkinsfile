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
                     sh './mvnw sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=loginHASH -DskipTests'                      
                 }
             }
        }
    }
}

