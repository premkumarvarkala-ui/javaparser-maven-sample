
pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {

        stage("Clean Workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Git Checkout") {
            steps {
                git branch: 'main',
                    url: 'https://github.com/premkumarvarkala-ui/javaparser-maven-sample.git'
            }
        }

        stage("Maven Version") {
            steps {
                sh 'mvn -version'
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
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
