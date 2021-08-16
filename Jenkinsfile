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
        sh 'sudo docker build . -t node-hello:$BUILD_ID'
      }
    }

    stage('Push') {
      steps {
        sh '''sudo docker login -u hagerim -p tchgsar3
sudo docker tag node-hello:$BUILD_ID hagerim/node-hello:$BUILD_ID 
&& sudo docker push hagerim/node-hello:$BUILD_ID 
'''
      }
    }

  }
}