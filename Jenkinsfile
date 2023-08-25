pipeline{
    agent any
    tools {
        terraform 'terraform'
    }
    stages{
        stage('checkout from GIT'){
            steps
            {
                   //withCredentials([usernamePassword(credentialsId: 'testing-git_hub', usernameVariable: 'karthiksaki', passwordVariable: 'Abc@12353**')])
                    //{
                        //sh "git clone https://" + gitUser + ":" + gitToken + "@github.com/karthiksaki/terraform-learning.git --branch master"
                        git branch: 'main', credentialsId: 'jenkinscid', url: 'https://github.com/karthiksaki/terraform_code.git'
                    //}
            
            }
        }
        stage('Terraform Init'){
            steps{
                sh 'terraform init'
            }
        }
        stage('Terraform Plan'){
            steps{
                sh 'terraform plan'
            }
        }
         stage('Terraform Apply'){
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
        // stage('Terraform Destroy'){
        //     steps{
        //         sh 'terraform destroy --auto-approve'
        //     }
        // }
       
    }
}
    post {
        always {
            cleanWs()
            deleteDir()
        }
}
