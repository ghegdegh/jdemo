pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building on branch: ${env.BRANCH_NAME}"
                sh 'echo Running build...' // Replace with your build command
            }
        }

        stage('Test') {
            steps {
                echo "Running tests on branch: ${env.BRANCH_NAME}"
                sh 'echo Running tests...' // Replace with test command
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying from main branch"
                sh 'echo Deploying...' // Replace with deploy script
            }
        }
    }
}
