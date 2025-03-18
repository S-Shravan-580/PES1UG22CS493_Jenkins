pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Trigger the PES1UG22CS493-1 Jenkins job
                    build job: 'PES1UG22CS493-1', wait: true

                    // Compile the C++ file
                    sh 'g++ -o main main.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run the compiled C++ program
                    sh './main'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...' // Placeholder for actual deployment steps
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
