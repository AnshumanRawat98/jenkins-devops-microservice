pipeline {
	agent {docker { image 'python:latest'}}
	stages{
		stage('Try Run Python'){
			steps {
				sh "python launch.py"
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