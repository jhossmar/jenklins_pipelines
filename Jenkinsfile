pipeline {
    agent {label 'Node1'}
    options {
         buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3')
    }

    environment{
        SERVICE_NAME="myapp-dj"
    }
    stages {
        stage('Build') {
            steps {
                script {
                   sh "cd /home/marcelo/Desktop/django/mysite; docker build -t 192.168.100.145:8082/${env.SERVICE_NAME}:${BUILD_NUMBER} . ; docker push 192.168.100.145:8082/${env.SERVICE_NAME}:${BUILD_NUMBER}"
                   sh "docker image rm 192.168.100.145:8082/${env.SERVICE_NAME}:${BUILD_NUMBER}"
                    
                }
                    
            }
        }
    }
}
