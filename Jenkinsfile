  
pipeline{
    agent any
    tools {
        terraform 'terraform-12.26'
    }
    stages{
        stage("Git Checkout"){
            steps{
                git credentialsId: 'git-token', url: 'https://github.com/dinhash/Jenkins'
            }
        }
	stage("Terraform init"){
			      steps{
				         sh label: '', script: 'terraform init'
			       }
		     }
       	stage("Terraform apply"){
			        steps{
				          sh label: '', script: 'terraform apply --auto-approve'
			        }
		    }
	stage("Terraform destroy"){
			        steps{
				          sh label: '', script: 'terraform destroy --auto-approve'
			        }
		    }
    }
}
