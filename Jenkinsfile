pipeline {
	//agent any
	agent { docker { image 'node:17.1.0'}}
stages {
	    		stage('Build') {
					steps{
						sh 'node --version'
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
