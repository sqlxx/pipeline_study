pipeline {
  agent any
  environment {
    scannerHome = tool 'SonarQubeScanner'
  }
  stages {
    stage('SCM') {
      steps {
        git branch:'master', url: 'git@gitee.com:maycur_doa/devops_platform.git', credentialsId:'github'
      }
    }
    stage('Sonar Scan') {
      steps {
        withSonarQubeEnv('sonar') {
          sh "${scannerHome}/bin/sonar-scanner  -Dsonar.projectKey=CRB"
        }
      }
    }
  }
}
