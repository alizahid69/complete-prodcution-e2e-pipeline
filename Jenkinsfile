pipeline{
    agent{
        label "jenkins-agent"
    }
    tools{
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("cleanup Workspace"){
            steps {
                cleanWs()
            }
        }
        stage("Checkout from SCM"){
            steps{
                git branch: 'main', credentialsId: 'alizahid', url: 'https://github.com/alizahid69/complete-prodcution-e2e-pipeline'
            }
        }
        stage("Build Application"){
            steps{
                sh "mvn clean pacakge"
            }
        }
        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}