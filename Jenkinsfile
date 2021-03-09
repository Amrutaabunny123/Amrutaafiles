pipeline {
  agent any
  stages {
    stage('Build'){
      steps {
        echo 'Building process Starts...'
        sh 'mvn clean package'
        echo 'Building process Ends'
      }
      post {
        success {
          echo 'Now Archiving...'
          archiveArtifacts artifacts: '**/*.war'
        }
      }
    }

    stage('Init'){
      steps {
        echo 'Testing Process starts'
        echo 'Api Testing Process'
        echo 'Functional Testing Process '
        echo 'Performance Testing Process'
        echo 'Testing Process Ends'
      }
    }

    stage('Deploy to staging - ITF'){
      steps {
        echo 'ITF Deployment Starts'
        build job: 'itf deploy'
        echo 'Staging Deployment completes...'
      }
    }
}
}
