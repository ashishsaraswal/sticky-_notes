pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This checks out the code from the repository
                checkout scm
            }
        }

        stage('Zip Repository') {
            steps {
                script {
                    // Assuming you're on a Unix-like agent (like Linux)
                    sh 'zip -r repository.zip .'
                }
            }
        }
    }

    post {
        always {
            // Archive the zip file so you can download it from Jenkins UI
            archiveArtifacts artifacts: 'repository.zip', allowEmptyArchive: true
        }
    }
}