def gv_script
pipeline {
    agent any
    environment {
         GITHUB_URL = "https://github.com/prabhat-roy/petshop_app_deployment_EKS_AWS_using_maven_jenkins_terraform.git"
         BRANCH = "main"
    }    
    stages {
        stage("Init") {
            steps {
                script {
                    gv_script = load"script.groovy"
                }
            }
        }        
        stage("Checkout from Git Repo") {
            steps {
                script {
                    gv_script.checkout()
                }
            }
        }
        
    }
}
