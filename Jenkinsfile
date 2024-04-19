pipeline{
  agent any
  stages {
    stage('Build') {
      steps{
        script{
          bat "mvn clean"
        }
      }
    }
    stage('Package') {
      steps{
        script{
          bat "mvn package"
        }
      }
    }
    stage('archieve') {
      steps{
        archiveArtifacts artifacts: "**/*.jar"
      }
    }
    
  }
}
