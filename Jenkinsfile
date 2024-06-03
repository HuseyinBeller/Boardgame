pipeline {
    agent any
    
    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

 stages {
        stage('Git Compile') {
          when {
                branch 'develop'
            }
            steps {
            sh 'mvn compile'
                input message: compiling the code;
            }
        }
            
         stage('Unit Test cases') {
            steps {
                sh 'mvn test'
            }
        }
        
         stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
