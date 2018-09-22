pipeline {
    agent any
    stages {
        stage('Setup') {
                steps {
                        echo 'Hi, this is Ernest from EMSYS Solution!!!'
			
                }
        }
	    stage('Build'){
		    
		steps {
			input('Do you want to proceed?')
        }
	    }
        stage('Code Review')  {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello Code Review"
                        }
        }
        stage('Test') {
                parallel {
                        stage('Unit Test') {
                                steps{
                                        echo "Running the unit test..."
                                }
                        }
                        stage('Integration test') {
				steps {
					echo 'Running the integration test..'
				}
                               
			}  }
        }
    }
}

