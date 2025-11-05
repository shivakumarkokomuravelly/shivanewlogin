pipeline {
    agent any
    triggers { pollSCM('*/2 * * * *') }
    
    stages {
        stage('cloning the repo') {
            steps {
                git branch: 'main', url: 'https://github.com/shivakumarkokomuravelly/shivanewlogin.git'
            }
        }
        stage('building the code') {
            steps {
                sh 'mvn package'
            }
        }   
        stage('archiving the artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }   
    }
}
