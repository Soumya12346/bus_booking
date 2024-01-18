pipeline {
    agent { label 'slave' }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf bus_booking.git'
                sh 'https://github.com/Soumya12346/bus_booking.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
        stage('deploy'){
            steps{
               sh 'ssh root@172.31.46.201'
               sh 'scp /home/slave/workspace/Samplepipeline/target/hello-world-war-1.0.0.war root@172.31.46.201:/opt/apache-tomcat-8.5.98/webapps/'
            }
        }    
    }
}

