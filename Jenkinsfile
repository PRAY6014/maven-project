pipeline {
    agent any
    stages{
        stage('Init'){
            steps {
                echo 'Init...'
            }
        }
        stage('Build'){
            steps {
                sh 'make'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('Deploy'){
            steps {
                echo 'Deploy...'
            }
        }
    }
}
