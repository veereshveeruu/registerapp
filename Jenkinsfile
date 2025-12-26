pipeline {
    agent { label 'Jenkins-Agent'}
    tools{
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup workspace") {
            steps {
                cleanWs()
            }
        }
        stage ("checkout from SCM"){
            steps {
                git
            }
        }
        stage("Build") {
            steps {
                 sh "mvn clean package"
            }
        }
        stage("Test") {
            steps{
                sh "mvn test"
            }
        }
        

    }
}
