pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo \'make package\''
      }
    }
    stage('Test') {
      steps {
        sh 'echo \'make check\''
      }
    }
    stage('Deploy') {
      when {
        tag 'release-*'
      }
      steps {
        echo 'Deploying only because this commit is tagged...'
        sh 'echo \'make deploy\''
      }
    }
  }
}