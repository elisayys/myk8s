pipeline {
    agent any
    

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
        stage("deploy to product") {
          when {
            branch 'product'
            steps {
              echo 'deploy to product'
            }
          }
        } 
          
    }
}
}
