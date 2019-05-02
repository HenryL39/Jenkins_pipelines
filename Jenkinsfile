pipeline {
    agent any
    environment {
        Nom="Je suis maven"
    }
    options {
        timeout(time: 5, unit: 'SECONDS')
        retry(3)
    }
    parameters {
        string(name: 'LOGIN', defaultValue: 'Jason', description: 'Username : ')
        password(name: 'PASSWORD', defaultValue: 'BOURNE', description: 'password : ')
    }
    stages {
        stage('checkout') {
            environment {
                prenomcheckout="Bernard"
            }
            steps {
                echo "$Nom, $prenomcheckout"
            }
        }
        
        stage('test') {
            environment {
                prenom="Claude"
            }
            steps {
                echo "$LOGIN, $PASSWORD"
            }
        }
        
        stage('deploy') {
            environment {
                prenom="alfred"
            }
            steps {
                echo "$Nom, $prenom"
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