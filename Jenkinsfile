@Library('my-shared-library') _

pipeline {
    
    agent any
    
    options {
        buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
    }
    
    stages {
        stage('Saludo') {
            steps {
                hello "${env.BUILD_USER}"
            }
        }
        
        stage('Var Function') {
            steps {
                script {
                    echo varList.equipoFutbol()
                    echo varList.equipoBasket()
                    echo varList.sistemaOperativo()
                }
                
            }
        }

        stage('Var List') {
            steps {
                script {
                    echo global.FUTBOL
                    echo global.SYSTEM
                    echo global.SERIE
                    echo global.LAPTOP
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
