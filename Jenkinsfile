pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS912-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                // Introduce a syntax error here
                sh './output || non_existent_command'
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
            error 'Pipeline failed'
        }
    }
}
