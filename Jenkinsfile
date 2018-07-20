pipeline {
  agent {
    docker {
      image 'alainchiasson/molecule'
    }
  }
  stages {
    stage ("create.") {
      steps {
        sh 'molecule --debug create'
      }
    }
    stage ("converge.") {
      steps {
        sh 'molecule --debug converge'
      }
    }
  }
}
