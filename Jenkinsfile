pipeline{
    agent any
    tools{
        maven 'local_maven'
    }
    stages{
        stage('build'){
            steps{
                sh 'whoami'
                sh 'mvn clean package'
                sh "/usr/local/bin/docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}
