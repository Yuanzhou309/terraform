pipeline {
    agent any
	
	
		parameters {

		booleanParam defaultValue: true, description: 'terraform apply', name: 'TerraformApply'
		booleanParam defaultValue: true, description: 'true to run img', name: 'TerraformDestroy'

		
		
		}

	
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
                 sh 'sudo terraform destroy -auto-approve'
		
            }
	 }
    

   
  
	    
	    
	    
	    
    }

	
	
	
	
	
	
	
	
post {
  always {
	  cleanWs()

  }
}
	

	
}
