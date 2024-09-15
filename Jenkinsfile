pipeline {
  agent any
  stages {
    stage('Stage 2') {
      steps {
        echo 'Hello Stage 2'
      }
    }

    stage('Stage 3') {
     when {
        expression {
           currentBuild.result == 'FAILURE' 
         }
      }
      steps {
          echo 'Stage 2 failed. Hello Stage 3'
      }
    }
    

    post {
        always {
            stage('Stage 4') {
                steps {
                    echo 'Hello Stage 4'
                }
            }
        }
    }
    
  }
}
