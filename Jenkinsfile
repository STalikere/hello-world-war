pipeline {
    agent {
        label "Slave2"        
    }
    stages {
        stage('install tomcat') {
            steps {
                sh 'chmod 755 ${WORKSPACE}/hello-world-war/TomcatScript'
                sh '${WORKSPACE}/hello-world-war/TomcatScript'
            }
        }
        stage('clone') {
            steps {
                sh 'restart'
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/STalikere/hello-world-war.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy') {
             steps {
                 sh 'sudo cp /${WORKSPACE}/target/hello-world-war-1.0.0.war /var/lib/tomcat9/webapps'
            }
        }
    }
}
