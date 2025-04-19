pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo "Building the MAIN branch..."
                    } else if (env.BRANCH_NAME == 'develop') {
                        echo "Building the DEVELOP branch..."
                    } else {
                        echo "Skipping build for unsupported branch: ${env.BRANCH_NAME}"
                        currentBuild.result = 'SUCCESS'
                        return
                    }
                }
            }
        }

        stage('Deploy') {
            when {
                expression {
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'develop'
                }
            }
            steps {
                script {
                    echo "🚀 Deploying ${env.BRANCH_NAME} branch..."
                   // Add your deployment step
                    echo "Deployment complete for ${env.BRANCH_NAME}"
                }
            }
        }
    }
}
