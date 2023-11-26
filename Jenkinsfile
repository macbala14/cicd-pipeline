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

    stage('Build') {
      steps {
        script {
          sh scripts/build.sh
        }

      }
    }

  }
  environment {
    env = 'mbala14/ci-cd-task'
  }
}
