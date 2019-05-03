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
                git branch: 'first_JenkinsFile', credentialsId: 'HenryL39', url: 'https://github.com/HenryL39/Jenkins_pipelines.git'
            }
        }
        
        stage('build') {
            steps {
                sh 'mvn -f pom.xml -s settings.xml compile'
            }
        }
        
        stage('test') {
            when {
                stage('build') == SUCCESS
            }
            steps {
                sh 'mvn -f pom.xml -s settings.xml test'
            }
            
        }
        
        stage('deploy') {
            steps {
                sh 'mvn -f pom.xml -s settings.xml deploy'
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
