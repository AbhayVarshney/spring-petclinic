pipeline {

   agent any

   stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh './mvnw package sonar:sonar -DskipTests -Dserver.port=8888'
            }
        }

        stage('Run') {
             steps {
                 sh 'java -Dserver.port=8888 -jar target/*.jar'
             }
        }

        stage('Scan') {
             steps {
                 withSonarQubeEnv(installationName: 'sq1') {
                     sh './mvnw sonar:sonar -Dsonar.host.url=http://localhost:9000 -DskipTests'                      
                 }
             }
        }
    }
}

