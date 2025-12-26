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
                git branch: 'main' , credentialsId: '41e56d3f-0683-4187-961a-3b5afe296bce', url: 'https://github.com/veereshveeruu/registerapp.git'
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
