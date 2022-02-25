pipeline {
    agent any

    environment{
            service_name = "nodejs-helloworld"
            docker_repo = "manikdevop"

    }

    stages {
        stage('build') {
            steps  {
                script {
                  sh  """ docker build -t ${docker_repo}/${service_name}:latest . """
                }
               
            }
        }
    }


    stages {
        stage('push to dockerhub') {
            steps  {
                script {
                  sh  """ docker push ${docker_repo}/${service_name}:latest . """
                }
               
            }
        }
    }
}
