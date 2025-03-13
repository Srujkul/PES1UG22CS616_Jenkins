pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output PES1UG22CS616.cpp' // Compile the C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './non_existing_file' // Intentional error: file does not exist
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...' // This stage should be skipped if Test fails
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
