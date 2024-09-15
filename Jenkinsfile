pipeline {
    agent any
    
    stages {
        stage('Stage 1') {
            steps {
                echo 'This is Stage 1'
            }
        }

        stage('Stage 2') {
            steps {
                script {
                    // Simulate failure for testing purposes
                    echo 'This is Stage 2'
                    // Uncomment the next line to simulate a failure
                    // error('Stage 2 failed')
                }
            }
        }

        stage('Stage 3') {
            when {
                expression {
                    // Only run Stage 3 if Stage 2 failed
                    return currentBuild.previousBuild?.result == 'FAILURE'
                }
            }
            steps {
                echo 'Stage 2 failed, so running Stage 3'
            }
        }
    }

    post {
        always {
            echo 'This will always run at the end of the pipeline.'
        }
    }
}
