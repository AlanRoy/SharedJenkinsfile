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
                    echo status.FUTBOL
                    echo status.SYSTEM
                    echo status.SERIE
                    echo status.LAPTOP
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
