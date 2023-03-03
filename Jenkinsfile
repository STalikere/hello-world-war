pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                sh 'rm -rf hello-world-war'
               // sh 'docker rm -f tomcat-image'
                sh 'git clone https://github.com/STalikere/hello-world-war.git'
            }
        }
//         stage('Build') {
//             steps {
//                 sh 'sudo mvn clean package'
//             }
//         }
        stage('Deploy') {
             steps {
                 sh 'docker run -d -p 8070:8080 tomcat-image'
            }
        }
    }
}
