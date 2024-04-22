pipeline{
  agent any
  triggers{
    pollSCM('* * * * *')
  }
  stages {
    stage('Build') {
      steps{
        script{
          bat "mvn clean"
        }
      }
    }
    stage('Package') {
      when {
        allOf{
        branch 'master'
        changeset '**'
        }
      }
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
