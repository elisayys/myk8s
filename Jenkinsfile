pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        stage('Build docker 镜像') {
            steps {
                sh "/root/script/build-image.sh"
            } 
        stage('K8S 应用新镜像') {
            steps {
                sh "/root/script/deploy.sh"
            }        

        post {  // 这是可选的
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
