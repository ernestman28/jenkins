pipeline {
    agent any
    stages {
        stage('Setup') {
                steps {
                        echo 'Perform Setup Steps!!!'
                }
        }
	stage('Build') {    
		steps {
			echo 'Build'
                }
	}
        stage('Test: Functional')  {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello Test: Functional"
                }
        }
        stage('Test: load-&-security') {
                parallel {
                        stage('Unit Test') {
                                steps{
                                        echo "Running unit test..."
                                }
                        }
                        stage('Integration test') {
				steps {
					echo 'Running integration test..'
				}        
			}  
                }
        }
        stage('Approval') {
                input('Do you want to proceed?')
        }
        stage('Deploy: TEST Tenant') {
                
        }
    }
}

