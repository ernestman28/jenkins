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
                        powershell ".\funcional_tests.ps1"
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
        stage('Approval') {
                steps {
                        input('Do you want to proceed?')
                }
        }
        stage('Deploy: TEST Tenant') {
                steps {
                        echo 'Deploy to TEST'
                }
        }
    }
}

