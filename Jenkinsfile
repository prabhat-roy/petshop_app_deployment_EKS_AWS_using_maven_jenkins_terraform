def gv_script
pipeline {
    agent any    
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
