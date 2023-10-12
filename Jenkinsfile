pipeline {
    agent any
    stages {
        stage('version-control') {
            steps {
                checkout ([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'etechapp-id', url: 'https://github.com/Team7-Etechapp/group-repo-project.git']]])
            }
        }
        stage('parallel-job') {
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