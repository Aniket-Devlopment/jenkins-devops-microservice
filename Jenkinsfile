//SCRIPTED JENKINS PIPELINE
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Integration Test"
// 	}

//DECLARATIVE JENKINS PIPELINE
pipeline {
	agent any
	stages {
		stage('Build'){
			steps {
				echo "Build"
				echo "Test"
				echo "Integration Test"
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
			echo 'I am Awesome. I run Always'
		}
		success {
			echo 'I run when you successful.'
		}
		failure {
			echo 'I run when you fail.'
		}
	}
}