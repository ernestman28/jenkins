pipeline {
    agent any
    environment {
        OUTPUT_PATH = 'C:\Repos\spo-intranet'
    }
    stages {
        stage('Setup') {
                steps {
                        echo 'Perform Setup Steps!!!'
                }
        }
	stage('Build') {    
		steps {
			echo 'Build'
                        //powershell "C:\repos\spo-intranet\NT.Intranet\NT.Intranet\NT.Deployment\CI_Install.ps1" -tenant "NT_TEST_GULP"
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

