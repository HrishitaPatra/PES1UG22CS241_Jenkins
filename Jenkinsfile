pipeline {
    agent any
    stages {        
        stage('Build') {
            steps {
                build 'PES1UG22CS241-1'
                sh 'g++ pipeline_test.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
                purposeful error
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
