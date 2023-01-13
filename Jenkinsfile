pipeline {
    agent any
	

	
    stages {
	    
        stage('terraform apply') {
        
         when {
		     expression {return params.TerraformApply}
	     }
            steps {

                echo 'terraform apply'	
                sh 'sudo terraform init'
                sh 'sudo terraform validate'
		            sh 'sudo terraform apply -auto-approve'
            }
        }
	    
	    
	    
     stage('terraform destroy') {
	     when {
		     expression {return params.TerraformDestroy}
	     }
            steps {
                echo 'terraform destroying'
                 sh 'sudo terraform destroy'
		
            }
	 }
    

   
  
	    
	    
	    
	    
    }

	
	
	
	
	
	
	
	
post {
  always {
	  cleanWs()
   sh'docker stop nodejs'
   sh 'sudo docker rm -vf $(sudo docker ps -aq) &>/dev/null'
  }
}
	

	
}
