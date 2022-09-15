pipeline {
  agent any
  
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'Maven3') {
          sh 'mvn clean install'
        }
      }
    }

    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}
