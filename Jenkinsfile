pipeline {
    agent any
       
    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

    stages {
        stage('Git Compile') {
          steps {
                sh 'mvn compile'
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
