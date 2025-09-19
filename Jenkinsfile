pipeline {
  agent any

  stages {
    stage ('Checkout') {
      steps {
        git url: 'https://github.com/francois-sa-semifir/test-demo-node-jenkins.git', branch: 'main'
      }
    }

    stage ('Install dependencies') {
      steps {
        sh 'npm ci'
      }
    }

    stage ('Run test') {
      steps {
        sh 'npm test'
        junit 'junit.xml'
      }
    }
  }

  post{
    always { echo 'Fin du pipeline'}
    success { echo 'tests OK !'}
    failure { echo 'tests KO !'}
  }

}
