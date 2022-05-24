pipeline {
	agent any
	//{ docker {image 'maven:3.6.3'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps {
				sh 'mvn --version'
				sh 'docker version'
			}
		}
		stage('Build'){
			steps {
				echo "Compile"
				sh 'mvn clean compile'
			}
		}
		stage('Test'){
			steps {
				echo "Test"
				sh 'mvn test'
			}
		}
		stage('Integration Test'){
			steps {
				echo "Integration Test"
				sh 'mvn failsafe:integration-test failsafe:verify'
			}
		}
	} 
	post {
		always {
			echo "I run always"
		}
		success {
			echo "I run only when you succeed"
		}
		failure {
			echo "I run only when you fail"
		}
	}
}