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
          sh '''
            sudo chmod 777 ./scripts/build.sh
            ./scripts/build.sh
            '''
        }

      }
    }

  }
  environment {
    env = 'mbala14/ci-cd-task'
  }
}
