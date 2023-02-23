pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }
	//agent { docker { image 'liferay/portal:latest' } }
	//docker pull liferay/portal:latest
	stages {
		stage('Build'){
			steps {
				//sh 'node --version'
				echo "Build"
				echo "$PATH"
				echo "Build number : $env.BUILD_NUMBER"
				echo "build id : $env.BUILD_ID"
				echo "job name : $env.JOB_NAME"
				echo "build tag : $env.BUILD_TAG"
				echo "build url : $env.BUILD_URL"
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
			echo 'I am awesome. I run always.. Test Helloworld 111 '
		} 
		success {
			echo 'I run when you are successful.. Test Helloworld 111 '
		}
		failure {
			echo 'I run when you fail.. Test Helloworld  111 '
		}
	}
}
