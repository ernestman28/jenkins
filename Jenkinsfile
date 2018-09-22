pipeline {
    agent any {
            git branch: 'F_CI_Build', credentialsId: 'd6ce97b6-bb88-47bc-8223-c185a5164ac5', url: 'https://ernestman@bitbucket.org/nationaltrust/spo-intranet.git'
    }
    environment {
        OUTPUT_PATH = 'C:/Repos/spo-intranet'
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
                        powershell "C:/repos/spo-intranet/NT.Intranet/NT.Intranet/NT.Deployment/CI_Install.ps1"
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

