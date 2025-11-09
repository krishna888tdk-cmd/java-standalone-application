pipeline {
    agent any   
    stages {
        stage('Checkout') {
           git url: 'https://github.com/expertszen/java-standalone-application.git',
                    branch: 'main'
        }
        stage('Build') {
         bat 'mvn clean package'
        }
        
    }
}
