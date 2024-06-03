pipeline {
    agent any
    
    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

    stages {
        stage('compile') {
         checkout scm
        }
        stage('test')
          echo 'branch name ' + env.BRANCH_NAME
            if (env.BRANCH_NAME.startsWith("bug-fix")) {
                   echo "Compiling the environment before build"
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
