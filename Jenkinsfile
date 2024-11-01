@Library('my-shared-library') _

pipeline {
    
    agent any
    
    options {
        buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
    }
    
    stages {
        stage('Demo') {
            steps {
                hello "${BUILD_USER}"
            }
        }
        
        stage('Variables') {
            steps {
                script {
                    echo varList.equipoFutbol()
                    echo varList.equipoBasket()
                    echo varList.sistemaOperativo()
                }
                
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
