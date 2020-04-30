pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                
                bat "mvn clean -f ApiAutomation"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test -f ApiAutomation"
            }
        }
        stage('Deploy') {
            steps {
                bat "mvn package -f ApiAutomation"
            }
        }
    }
}