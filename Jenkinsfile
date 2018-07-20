pipeline {
  agent {
    docker {
      image 'alainchiasson/molecule'
    }
  }
  stages {
    stage ("Do a full test cycle.") {
      steps {
        sh 'molecule --debug test'
      }
    }
  }
}
