pipeline {
	agent any
	//agent { docker { image 'node:17.1.0'}}
	environment {
		dockerHome = tool 'Mydocker'
		mavenHome = tool 'My-maven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		
	}
stages {
	    		stage('Checkout') {
					steps{
						sh 'mvn --version'
						sh 'docker version'
						echo "Checkout"
					}
 				}
 				stage('Compile') {
					steps{
						sh 'mvn clean compile'
					}
 				}
 		 		stage('Test') {
					steps{
						sh 'mvn test' 
					}
				 }
				 stage('Integration Test') {
					steps{
						sh 'mvn failsafe:integration-test failsafe:verify'
					}
 				}
 				stage('Package') {
					steps{
						sh 'mvn package -DskipTests'
					}
				}
 				
 				stage('Build Docker image') {
					steps{
						//"docker build -t in28min/currency-exchange-devops:$env.BUILD_TAG"
						script{
						dockerImage = docker.build("ramadoc7/currency-exchange-devops:${env.BUILD_TAG}")
						}
					}
 				}
 				stage('Push Docker image') {
					steps{
						script{
							docker.withRegistry('','dockerhub'){
								dockerImage.push();
								dockerImage.push('latest');
								}
						}
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