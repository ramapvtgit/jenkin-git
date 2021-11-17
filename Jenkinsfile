pipeline {
	agent any
	//agent { docker { image 'node:17.1.0'}}
	environment {
		dockerHome = tool 'Mydocker'
		mavenHome = tool 'My-maven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		
	}
stages {
	    		stage('Build') {
					steps{
						sh 'mvn --version'
						sh 'docker version'
						echo "Build"
					}
 				}
 		 		stage('Test') {
					steps{
						echo "Test"
					}
				 }
				 stage('Integration Test') {
					steps{
						echo "Integration Test"
					}
 				}
 		
 	} 	
 post {
 		always {
 		echo 'I am awesome'
 		}
 		success {
 		echo 'I am success'
 		}
 		failure {
 		echo 'I am failure'
 		}
 
 }
}
