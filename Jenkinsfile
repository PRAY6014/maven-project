pipeline {
    agent any
    
    tools{
maven 'localmaven'
jdk 'localjdk'
}
    stages{
        stage('Init'){
            steps {
                echo 'Init...'
            }
        }
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to Staging'){
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}
