pipeline {
	agent any
	       environment {
		 CI = 'true'
        }
	stages {
		stage('Build') {
			agent {
				docker {
					image 'node:6-alpine'
					args  ' -p 3000:3000'
				       }
				}
			steps {
			    sh  'npm install'
			}
		}
		stage('Sonarqube') {
			agents any
			environment{
				scannerHome = tool 'SonarQube'
			}
			Steps {
			     withSonarQubeEnv('sonarqube') {
				sh "${scannerHome}/bin/sonar-scanner"
				}
				timeout(time: 10, unit: 'MINUTES') {
					waitForQualityGate abortPipeline: true
				}
			}
		}
		}
}
		node {
	   def app

	stage('Build image') {
	app = docker.build("ammar21/coursework_2")
     }

	stage('Push image') {
	docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}								
					
		
			
			
