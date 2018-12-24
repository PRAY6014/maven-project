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
                echo '$PATH'
                sh 'mvn package'
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
