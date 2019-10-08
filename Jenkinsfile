pipeline{
    agent any
    tools{
        maven 'local maven'
    }
    stages{
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
            post{
                success{
                    echo '构建成功，开始存档'
                    archiveArtifacts artifacts:'**/target/*.war'
                }
            }
        }
        stage('Depoly to staging'){
            steps{
                build job:'maven-war-deploy'
            }
        }
    }
}
