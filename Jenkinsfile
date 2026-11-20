
pipeline {
    agent {
        label "worker-1"
    }

    tools {
        maven 'Maven-3.9'
    }

    stages {

        stage("Clean Workspace") {
            steps {
                cleanWs()
            }
        }

        }

        stage("Maven Build") {
            steps {
                sh 'mvn clean package'
            }
        }

        stage("Verify Build") {
            steps {
                sh 'ls -lh target/'
            }
        }
    }

    post {
        success {
            echo 'Maven build completed successfully!'
        }

        failure {
            echo 'Maven build failed!'
        }
    }

