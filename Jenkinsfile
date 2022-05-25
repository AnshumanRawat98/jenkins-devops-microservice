pipeline {
	agent any
	stages{
		stage('Initialisation'){
			steps {
				sh "docker version"
				sh "python --version"
				sg "python launch.py"
			}
		}
		stage('Building Image'){
			steps {
				script{
					dockerImage=docker.build("anshumanrawat/pythontest:latest")
				}
			}
		}
		stage('Pushing Image'){
			steps {
				script{
					docker.withRegistry('', 'Docker') {
						dockerImage.push('latest')
					}
				}
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