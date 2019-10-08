pipeline{
    agent any
    tools{
        maven 'local_maven'
    }
    stages{
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Depoly to docker'){
            steps{
                sh 'docker build . -t tomcatwebapp:${env.BUILD_ID}'
            }
        }
    }
}
