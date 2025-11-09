pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                // If this job is "Pipeline script from SCM", you can also use: checkout scm
                git url: 'https://github.com/krishna888tdk-cmd/java-standalone-application.git',
                    branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Windows agent → use bat
                bat 'mvn install package'
            }
        }

        stage('Run Application') {
            steps {
                // Adjust jar name if your pom gives a different finalName
        bat 'java -jar target/java-standalone-application-1.0-SNAPSHOT.jar'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }
}
