pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build job: 'PES1UG22CS493-1', wait: true

                    
                    sh 'g++ -o a main.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    
                    sh './a'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...' 
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
