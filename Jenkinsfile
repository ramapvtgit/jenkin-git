pipeline {
	agent any
stages {
	    		stage('Build') {
					steps{
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
