pipeline {
    agent any
    stages {        
        stage('Build') {
            steps {
                echo 'Hello, Maven'
                sh 'mvn clean install'
            }
        }
    }
}
