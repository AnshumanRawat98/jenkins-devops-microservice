pipeline {
	agent any
	stages{
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