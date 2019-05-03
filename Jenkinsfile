pipeline {
	agent any
	options {
        	parallelsAlwaysFailFast()
    	}
	stages {
	stage ('non seq') {
		steps {
			echo "non sequentiel"
		}
	}

	when {
		branch 'branch1'
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
					echo "Sequence 2"
				}
			}

			stage ('Sequence 3') {
				steps {
					echo "Sequence 3"
				}
			}
		}
	}
	when {
		branch 'branch2'
	}
	stage('parrallel') {
		tools {
			maven 'maven'
		}
		failFast true
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
	when {
		branch 'branch2'
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
