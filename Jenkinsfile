Pipeline {
	agent any
	       stages{
		    stage('Build image') {
			app = docker.build("ammar21/coursework_2")
			}
		   stage('Push image'){
                         docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                         app.push("latest")
			}
	          
               
					
		         
 		       }
   		}
}								
					
		
			
			
