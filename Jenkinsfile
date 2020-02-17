pipeline {
  agent { docker 'python:3.7.6'}
  stages {
    state('build') {
      steps {
        sh 'python --version'
      }
    }
  }
}
