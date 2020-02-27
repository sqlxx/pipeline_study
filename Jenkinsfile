pipeline {
  agent any
  environment {
    sannerHome = tool 'SonarQubeScanner'
  }
  stages {
    stage('SCM') {
      steps {
        git branch:'master', url: 'ssh:git@gitee.com:maycur-backend/maycur-id-service.git', credentialsId:'gitee'
      }
    }
    stage('Sonar Scan') {
      steps {
        withSonarQuteEnv('sonarqube') {
          sh "${scannerHome}/bin/sonar-scanner  -Dsonar.projectKey=CRB"
        }
      }
    }
  }
}
