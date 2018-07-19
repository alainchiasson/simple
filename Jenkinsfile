pipeline {
  agent {
    docker {
      image 'retr0h/molecule:2.16'
    }
  }
  stages {
    stage ("Executing Molecule lint") {
      steps {
        sh 'sudo molecule --debug test'
      }
    }
  }
}
