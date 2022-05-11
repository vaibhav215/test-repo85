pipeline {
    agent {
        node{
        label 'linux-ec2-node'
        customWorkspace '/home/ec2-user/new-ws'
    
        }
    }

    stages {
        stage('clean') {
            steps {
                sh 'rm -rf /home/ec2-user/new-ws/*'
             }
        }
        stage('copy') {
            tools{
                jdk 'java 1.9.4'
            }
            steps {
                sh 'java -version'
                sh 'cp /home/ec2-user/jenkins-home/workspace/java-compile/Hello.java  /home/ec2-user/new-ws'
             }
        }
         stage('compile') {
             tools{
                 jdk 'java 1.9.0'
             }
            steps {
                sh 'java -version'
                sh 'javac Hello.java'
             }
        }
    }
}
