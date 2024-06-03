pipeline {
    agent any

    environment {
        GIT_CREDENTIALS_ID = https://github.com/HuseyinBeller/Boardgame.git
    }
    
    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

 stages {
    stage('Checkout') {
        when {
            branch 'develop'
        }
    }
     
        stage('Checkout') {
          when {
              // Checkout the develop branch
                    checkout([$class: 'GitSCM', branches: [[name: "*/develop"]],
                        doGenerateSubmoduleConfigurations: false,
                        extensions: [[$class: 'LocalBranch', localBranch: 'develop']],
                        submoduleCfg: [],
                        userRemoteConfigs: [[credentialsId: "${env.GIT_CREDENTIALS_ID}", url: 'git@your-repo-url.git']]
                    ])
            }
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
                echo 'Packaging and Testing develop branch'
            }
        }
    }
}
