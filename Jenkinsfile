pipeline {
  agent {
    docker {
      image 'retr0h/molecule:2.16'
    }
  }
  stages {
    stage ("Do a full test cycle.") {
      steps {
        sh 'sudo molecule --debug test'
      }
    }
  }
}
