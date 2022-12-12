//SCRIPTED JENKINS PIPELINE
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Integration Test"
// 	}

//DECLARATIVE JENKINS PIPELINE
pipeline {
	agent any

	environment{
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	// agent { docker { image 'maven:3.6.3'} }
	stages {
		stage('Checkout'){
			steps {
				sh "mvn --version"
				sh "docker version"
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"

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