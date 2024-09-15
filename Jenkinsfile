pipeline {
  agent any
  stages {
    stage('Stage 2') {
      steps {
        echo 'Hello stage2'
      }
    }

    stage('Stage 3') {
     when {
              expression {
                currentBuild.result == null || currentBuild.result == 'FAILURE' 
              }
            }
      steps {
          sh 'Stage 2 failed. Hello Stage 3'
      }
    }
  }
}
