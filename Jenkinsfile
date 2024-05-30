
pipeline {
    agent any
    tools{
        jdk 'OpenJDK8'
        maven 'Maven3'
        
    }
    stages {
        stage('SCM') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/sajal55/docker-spring-boot-java-web-service-example.git'
            }
        }
        stage('Maven Build') {
            steps {
                sh "mvn clean install"
            }
        }
        stage('Docker Build') {
            steps {
                script{
                    sh "docker build -t sajalsharma125/new-secret:tag1new3 ."
                    
                }
            }
        }
        stage('Docker Container') {
            steps {
                script{
                 // sh "docker run -d --name your-java-app -p 9090:9090 ${DOCKER_IMAGE}:${DOCKER_TAG}"
                    sh "docker run  -p 80:8080 sajalsharma125/new-secret:tag1new3"
                    
                }
            }
        }
        
    }
}
