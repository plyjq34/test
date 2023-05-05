node {
  stage('SCM') {
    git branch: 'main', credentialsId: '4a601cc3-972e-45dc-bb37-11e5ceeac314', url: 'https://github.com/plyjq34/test.git'
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarQube Scanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.java.binaries=. -Dsonar.projectKey=test -Dsonar.login=sqa_483a2a2440b92a60f01d8a3d9a516967bb78086d"
    }
  }
}
