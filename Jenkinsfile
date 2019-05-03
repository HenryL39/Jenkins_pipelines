pipeline {
	agent any
	stages {
		stage('parrallel') {
  			parallel {
  				stage('Parrallel 1') {
                    steps {
                        echo "Parrallel 1"
                    }
                }
                stage('Parrallel 2') {
                    steps {
                        echo "Parrallel 2"
                    }
                }
  			}
		}

		stage('parrallel v2') {
  			parallel {
  				stage('Parrallel v2 1') {
                    steps {
                        echo "Parrallel v2 1"
                    }
                }
                stage('Parrallel v2 2') {
                    steps {
                        echo "Parrallel v2 2"
                    }
                }
  			}
		}
	}
}
