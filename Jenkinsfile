pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git 'https://github.com/spring-projects/spring-petclinic'
                sh './mvnw clean compile'
            }
        }
    }
}

