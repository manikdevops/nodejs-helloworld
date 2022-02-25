pipeline {
    agent any

    environment{
            repo_name = "manikdevop/nodejs-helloworld"
            registryCredential = 'dockerhub_id' 
            dockerImage = ''

    }

    stages {
        stage('build') {
            steps  {
                script {
                  dockerImage = docker.build repo_name + ":latest" 
                }
               
            }
        }
    

        stage("push to dockerhub") {
            steps  {
                script {
                    docker.withRegistry( '', registryCredential ) { 
                         dockerImage.push() 

                    }
                }
               
            }
        }
    }
}
