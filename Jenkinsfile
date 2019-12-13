pipeline {
	agent any
	       stages{
		    stage('Build image') {
				steps{
					app = docker.build("ammar21/coursework_2")
				     }
			}
		   stage('Push image'){
			 steps{
                         docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                         app.push("latest")
                         }			
                         }
	          
               
					
		         
 		       }
   		}
}								
					
		
			
			
