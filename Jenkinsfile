pipeline {
  agent {'windows-latest'}
  options {
   buildDiscarder(logRotator(numTokeepStr:'5'))
  }
  stages{
    stages('Scan')
    {
      steps{
        withSonarQubeEnv(installation: 'SonarQube'){
        sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
        }
      }
    }
  }
}
