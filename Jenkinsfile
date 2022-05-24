pipeline {
	agent { label { docker {image 'maven:3.6.3' } } }
	stages {
		stage('Build'){
			steps {
				sh 'mvn --version'
				echo "this is maven version"
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
			echo "I run always"
		}
		success {
			echo "I run only when you succeed"
		}
		failure {
			echo "I run only when you fail"
		}
		changed {
			echo "I run when something changes"
		}
	}
}