pipeline {
    agent any

    stages {
        stage ("Fetch Code"){
            steps {
                git branch: 'main', url: 'https://github.com/rofiqirapsanjani/eks-irsa.git'
            }
        }
        stage ("terraform init") {
            steps {
                sh ('terraform init -reconfigure') 
            }
        }
        stage ("terraform plan") {
            steps {
                sh ('terraform plan') 
            }
        }
                
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
