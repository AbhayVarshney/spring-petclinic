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
                     sh './mvnw clean install sonar:sonar -Dsonar.projectKey=groupId:artifactId -Dsonar.host.url=http://localhost:9000 -Dsonar.login=loginHASH -Dsonar.sources=src/main/java/ -Dsonar.java.binaries=target/classes'

                      
                 }
             }
        }
    }
}

