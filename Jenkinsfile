pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            git url: 'https://github.com/expertszen/java-standalone-application.git',
                    branch: 'main'
        }
        stage('Build') {
            git url: 'https://github.com/expertszen/java-standalone-application.git',
                    branch: 'main'
        }
        stage('Run Application') {
            bat 'java -jar target/java-standalone-application.jar'
        }
        stage('Test') {
             bat 'mvn test'
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
