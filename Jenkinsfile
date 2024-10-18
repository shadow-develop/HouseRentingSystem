pipeline {
    agent any
        stages{
            stage('Build Project') {
                steps {
                        bat 'dotnet build'
                    }
                }

            stage('Execute Tests') {
                steps {
                        bat 'dotnet test --configuration Release'
                    }
             }
        }
    }