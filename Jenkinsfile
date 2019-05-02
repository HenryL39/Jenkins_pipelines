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
                git checkout([$class: 'GitSCM', branches: [[name: '*/first_JenkinsFile']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'HenryL39', url: 'https://github.com/HenryL39/Jenkins_pipelines.git']]])
            }
        }
        
        stage('test') {
            steps {
                sh 'mvn -v'
            }
        }
        
        stage('deploy') {
            steps {
                sh 'mvn -f pom.xml install'
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
