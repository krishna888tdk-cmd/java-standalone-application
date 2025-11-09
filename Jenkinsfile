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
        
    }
}
