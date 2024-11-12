def gv_script
pipeline {
    agent any
    tools {
        jdk 'Java'
        maven 'Maven'
    }
    environment {
         GITHUB_URL = "https://github.com/prabhat-roy/petshop_app_deployment_EKS_AWS_using_maven_jenkins_terraform.git"
         BRANCH = "main"
         SCANNER_HOME =tool "SonarQube"
         IMAGE_NAME = "petshop-image"         
         ACC_ID = "873330726955"
         REGION = "us-east-1"
         ECR = "${ACC_ID}.dkr.ecr.${REGION}.amazonaws.com"
    }
    stages {
        stage("Init") {
            steps {
                script {
                    gv_script = load"script.groovy"
                }
            }
        }
        stage("Clean Workspace") {
            steps {
                script {
                    gv_script.clean()
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
        
        stage("Kubernetes manifast update") {
            steps {
                script {
                    gv_script.update()
                }
            }
        }
        stage("Kubernetes deployment") {
            steps {
                script {
                    gv_script.deploy()
                }
            }
        }
    }
}
