 
pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/main']], 
                userRemoteConfigs: [[url: 'https://github.com/DarrenVeigas/CC/']]])
            }
        }

        stage('Build') {
            steps {
                sh 'g-- main/new.cpp -o output' 
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy' 
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
