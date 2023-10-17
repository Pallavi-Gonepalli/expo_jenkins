node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'M3';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=com.example:expo_jenkins -Dsonar.projectName='com.example:expo_jenkins' -Dsonar.host.url=http://localhost:9020 -Dsonar.token=sqp_ba3117ae9870dbb49aa82781b059798c6c3e8e0b"
    }
  }
}
