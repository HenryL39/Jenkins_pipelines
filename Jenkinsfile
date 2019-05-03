pipeline {
	agent any
	stages {
		stage ('non seq') {
			steps {
				echo "non sequentiel"
			}
		}
		
		stage('Sequentiels') {
  			stages {
				stage ('Sequence 1') {
					steps {
						echo "Sequence 1"
					}
				}

				stage ('Sequence 2') {
					steps {
						echo "Sequence 1"
					}
				}
				
				stage ('Sequence 3') {
					steps {
						echo "Sequence 3"
					}
				}
			}
		}
	}
}
