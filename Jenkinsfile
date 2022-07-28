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
                     sh 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=4a00d0a858589570d29be3d2371b2c31c8e9634b'                      
                 }
             }
        }
    }
}

