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
                     sh './mvnw sonar:sonar -Dsonar.host.url=http://localhost:9000 -DskipTests'                      
                 }
             }
        }

        stage('Run') {
             steps {
                 sh 'java -jar target/*.jar -Dserver.port=8888'
             }
        }
    }
}

