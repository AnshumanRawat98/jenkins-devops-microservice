pipeline {
	agent any
	stages{
		stage('Try Run Python'){
			steps {
				sh "python $PATH/launch.py"
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