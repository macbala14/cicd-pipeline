pipeline {
  agent any
  stages {
    stage('Git-checkout') {
      steps {
        script {
          checkout scm
        }

      }
    }

  }
  environment {
    env = 'mbala14/ci-cd-task'
  }
}