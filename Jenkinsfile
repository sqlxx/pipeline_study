pipeline {
  environment {
    sannerHome = tool 'SonarQubeScanner'
  }
  stages {
    stage('SCM') {
      steps {
        git url: 'ssh:git@gitee.com:maycur-backend/maycur-id-service.git'
      }
    }
    state('Sonar Scan') {
      withSonarQuteEnv('sonarqube') {
        sh "${scannerHome}/bin/sonar-scanner  -Dsonar.projectKey=CRB"
      }
    }
  }
}
