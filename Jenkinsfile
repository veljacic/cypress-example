pipeline {
  agent {
    docker {
      image 'cypress/base:10'
    }
  }

  stages {

    stage("Prepare") {
      steps {
        sh 'npm install --save-dev cypress'
        sh "${npm bin}/cypress verify"
      }
    }

    stage('Run cypress') {
      steps {
        sh "${npm bin}/cypress run"
      }
    }

  }

  post {
    always {
      deleteDir()
    }
  }
}