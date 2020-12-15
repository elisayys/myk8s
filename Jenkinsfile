 pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/elisayys/githubtest1.git'
            }
        }
        stage("deploy to master") {
              when {
                branch 'master'
              }
                steps {
                  echo 'deploy to master'
                }
              
            }

        stage("deploy to dev") {
          when {
            branch 'dev'
          }
            steps {
              echo 'deploy to dev'
            }
          
        } 
        stage("deploy to product") {
          when {
            branch 'product'
          }
            steps {
              echo 'deploy to product'
            }
          
        } 
     
}
}
