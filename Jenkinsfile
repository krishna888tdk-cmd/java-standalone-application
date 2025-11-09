pipeline {
    agent any   
    stages {
        stage('Checkout') {
            steps {
           git url: 'https://github.com/expertszen/java-standalone-application.git',
                    branch: 'main'
        }
        }
        
        stage('Build'){
        steps {
         bat 'mvn clean package'
        }
        }
        stage('Run Application') {
            steps {
                // Adjust jar name if your pom gives a different finalName
                bat 'java -jar target/java-standalone-application.jar'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }
}
