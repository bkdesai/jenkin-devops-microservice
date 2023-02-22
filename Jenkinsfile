pipeline {
	agent any
	stages {
		stage('Build'){
			steps {
				echo "Build"
			}
		}
		stage('Test'){
			steps {
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps {
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo 'I am awesome. I run always.. Test Helloworld'
		} 
		success {
			echo 'I run when you are successful.. Test Helloworld'
		}
		failure {
			echo 'I run when you fail.. Test Helloworld'
		}
	}
}
