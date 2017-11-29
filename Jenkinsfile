pipeline {
  agent {
    label 'slave1'
  }
  options {
    buildDiscarder(logRotator(numToKeepStr:'10', artifactNumToKeepStr:'2'))
  }

  stages{
    stage ('Check Maven Install'){
      steps {
        sh 'mvn -v'
      }
    }
    stage ('Running Unit Tests'){
      steps {
        sh 'mvn test'
        junit 'target/surefire-reports/*.xml'
      }
    }
    
  }
}
