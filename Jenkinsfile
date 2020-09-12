pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/elisayys/githubtest1.git'
            }
        stage("deploy to master") {
              when {
                branch 'master'
                steps {
                  echo 'deploy to master'
                }
              }
            }

        stage("deploy to dev") {
          when {
            branch 'dev'
            steps {
              echo 'deploy to dev'
            }
          }
        } 
        stage('Build docker 镜像') {
            steps {
                sh "/root/script/build-image.sh"
            } 
        stage('K8S 应用新镜像') {
            steps {
                sh "/root/script/deploy.sh"
            }        

    }
}

