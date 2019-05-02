pipeline {
    agent any
    options {
        retry(3)
    }
    tools {
        maven 'maven' 
    }
    stages {
        stage('checkout') {
            steps {
                git credentialsId: 'HenryL39', url: 'https://github.com/HenryL39/Jenkins_pipelines.git'
            }
        }
        
        stage('test') {
            steps {
                mvn test
            }
        }
        
        stage('deploy') {
            steps {
                mvn deploy
            }
        }
    }
    post {
        success {
            echo "Build completed successfully"
        }
        failure {
            echo "Task failed successfully"
        }
    }
}
