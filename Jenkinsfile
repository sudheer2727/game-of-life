pipeline {
    agent any
// stage
    stages {        
        stage('Build') {
            steps {
                echo 'Hello, Maven'
                sh 'mvn clean install'
            }
        }
    }
}
