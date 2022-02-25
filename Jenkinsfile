pipeline {
    agent any

    environment{
            service_name = "nodejs-helloworld"
            docker_repo = "manikdevop"
            registryCredential = 'dockerhub_id' 

    }

    stages {
        stage('build') {
            steps  {
                script {
                  sh  """ docker build -t ${docker_repo}/${service_name}:latest . """
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
