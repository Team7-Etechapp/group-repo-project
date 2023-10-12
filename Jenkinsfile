pipeline {
    agent any
    stages {
        stage('checkout-code') {
            steps {
               echo 'checking code from Git'
            }
        }
        stage('parallel') {
            parallel {
                stage('build') {
                    steps {
                        echo 'building'
                    }
                }
                stage('test') {
                    steps {
                        echo 'testing'
                    }
                }
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy will initiate after build and test'
            }
        }
    }
}