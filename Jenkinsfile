pipline {	
	agent any
	stages{
		stage('Build Application'){
		steps{
		sh 'mvn clean install'
		}
	}
		stage('Deploy Application to Mulesoft CloudHub'){
		steps{
		sh 'mvn package deploy -DmuleDeploy'
		}
	}
		stage('Performe Regression Testing'){
		steps{
		sh 'newman run /home/user/Postman/files/world-timezone-service.postman_collection.json -r htmlextra --reporter-htmlextra-export /home/user/Postman/files --reporter-htmlextra-darkTheme'
		}
	}
	}
}