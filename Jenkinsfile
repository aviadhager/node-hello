pipeline {
  agent {
    node {
      label 'centof7'
    }

  }
  stages {
    stage('CheckOut') {
      steps {
        git(url: 'https://github.com/aviadhager/node-hello.git', branch: 'master')
      }
    }

    stage('Build docker image') {
      steps {
        sh 'docker build . -t node-hello:${env.BUILD.ID}'
      }
    }

  }
}