pipeline {
	agent any
		stages {
			stage('One') {
				steps {
					echo 'Hi, This is Amit from DS.'
				}
			}
			stage('Two') {
				steps {
					input('Do you want to proceed?')
				}
			}
			stage('Three') {
				when {
					not {
						branch "master"
					}
				}
				steps {
					echo "Hello"
				}
			}
			stage('Four') {
				parallel {
					stage('unit Test') {
						steps {
							echo "Running unit test..."
						}
					}
					stage('Integration test') {
						agent {
							docker {
								reuseNode false
								image 'ubuntu'
							}
						}
						steps {
							echo 'Running the integration test'
						}	
					}
				}

			}

		}
}
