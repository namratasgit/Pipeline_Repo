pipeline {
	agent none
	stages {
		stage('Non-parallel Stage'){
			agent {
				label "built-in";
				}

			steps {
					echo 'This stage will be executed first';
				}
		}

		stage('Run Tests') {
			parallel {
				stage('Test on Windows') {
					agent {
						label "slave_node1";
					}

					steps {
						echo "Task1 on Agent";
					}
				}

				stage('Test on Master') {
					agent {
							label "built-in";
						}	
					steps {
						echo "Task1 on Master";
					}
				}

				
			}
		}
}
}
