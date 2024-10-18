pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                script {
                    echo 'Restoring .NET dependencies...'
                    // Restore the project dependencies on Windows
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the .NET project...'
                    // Build the project on Windows
                    bat 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running unit tests...'
                    // Run the unit tests on Windows
                    bat 'dotnet test --configuration Release'
                }
            }
        }
    }

    post {
        always {
            // Clean up workspace after build
            echo 'Cleaning up workspace...'
            cleanWs()
        }
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
