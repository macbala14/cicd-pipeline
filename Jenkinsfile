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
          sh 'scripts/build.sh'
        }

      }
    }

    stage('Tests') {
      steps {
        script {
          sh 'scripts/test.sh'
        }

      }
    }

    stage('Build-docker-image') {
      steps {
        script {
          docker.build("${registry}:${env.BUILD_ID}")
        }

      }
    }

    stage('Docker-image-push') {
      steps {
        script {
          docker.withRegistry('','dockerhub_id'){
            docker.image("${registry}:${env.BUILD_ID}").push('latest')
            docker.image("${registry}:${env.BUILD_ID}").push("${env.BUILD_ID}")
          }
        }

      }
    }

  }
  environment {
    registry = 'mbala14/ci-cd-task'
  }
}