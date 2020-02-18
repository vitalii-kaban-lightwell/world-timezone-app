pipeline {	
	agent any
	stages{
		stage('Build Application'){
		steps{
		sh 'mvn clean install'
		}
	}
		stage('Unit Testing'){
		steps{
		sh 'mvn test'
		}
	}
		stage('Deploy Application to Mulesoft CloudHub'){
		steps{
		sh 'mvn package deploy -DmuleDeploy'
		}
	}
		stage('Perform Regression Testing'){
		steps{
		sh 'newman run /home/user/Postman/files/world-timezone-service.postman_collection.json'
		}
	}
	
			stage('Deploy Application to Nexus Repo'){
		steps{
		sh 'mvn clean deploy'
		}
	}
	
	}
}