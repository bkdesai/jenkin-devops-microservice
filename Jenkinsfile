pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }
	//agent { docker { image 'liferay/portal:latest' } }
	//docker pull liferay/portal:latest
	environment{
		dockerHome = tool 'myDocker' 
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout'){
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "$PATH"
				echo "Build number : $env.BUILD_NUMBER"
				echo "build id : $env.BUILD_ID"
				echo "job name : $env.JOB_NAME"
				echo "build tag : $env.BUILD_TAG"
				echo "build url : $env.BUILD_URL"
			}
		}
		stage('Compile'){
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test'){
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package'){
			steps{
				sh "mvn package -DskipTests"
			}
		}
		stage('Build Docker Image'){
			steps {
				//"docker build -t in28min/currency-exchange-devops:$env.BUILD_TAG"
				script{
					dockerImage = docker.build("in28min/currency-exchange-devops:${env.BUILD_TAG}")
				}
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
