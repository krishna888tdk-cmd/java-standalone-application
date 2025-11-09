pipeline {
    agent any

    tools {
        jdk 'JDK21'
        bat 'mvn...'
    }

    stages {
        stage('Checkout') {
           git url: 'https://github.com/expertszen/java-standalone-application.git',
                    branch: 'main'
        }
        stage('Build') {
           // you are on Windows → use bat
                bat 'mvn clean package'
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
