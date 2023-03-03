pipeline {
    agent any
    stages {
         stage('Initialize'){
        steps {
                def dockerHome = tool 'myDocker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"                }
        }
        stage('clone') {
            steps {
                sh 'rm -rf hello-world-war'
               // sh 'docker rm -f tomcat-image'
                sh 'git clone https://github.com/STalikere/hello-world-war.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mvn_docker .'
                }
        }

        stage('Deploy') {
             steps {
                 sh 'docker run -d -p 8070:8080 tomcat-image'
            }
        }
    }
}
