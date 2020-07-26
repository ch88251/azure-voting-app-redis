pipeline {
  agent any

  stages {
    stage('Verify Branch') {
      steps {
        echo "$GIT_BRANCH"
      }
    }
    stage('Docker Build') {
      steps {
        sh(script: 'docker images -a')
        dir('azure-vote') {
          sh(script: 'docker build -t voting-pipeline .')
        }
      }
    }
  }
}
