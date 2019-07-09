pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('build') {
      steps {
        warnError(message: 'test') {
          cleanWs(cleanWhenAborted: true, cleanWhenFailure: true, cleanWhenSuccess: true)
        }

      }
    }
  }
}