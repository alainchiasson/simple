pipeline {
  agent {
    docker { image 'retr0h/molecule:2.16'}
  }

  stages {
    stage ("Executing Molecule lint") {
      steps {
        sh 'molecule lint'
      }
    }
    stage ("Executing Molecule create") {
      steps {
        sh 'molecule create'
      }
    }
    stage ("Executing Molecule converge") {
      steps {
        sh 'molecule converge'
      }
    }
    stage ("Executing Molecule idemotence") {
      steps {
        sh 'molecule idempotence'
      }
    }
    stage ("Executing Molecule verify") {
      steps {
        sh 'molecule verify'
      }
    }
  }
}
// node() {
//     try {
//         stage ("Get Latest Code") {
//             checkout scm
//             sh 'git rev-parse HEAD > .git/commit-id'
//         }
//         stage ("Executing Molecule lint") {
//             sh 'molecule lint'
//         }
//         stage ("Executing Molecule create") {
//             sh 'molecule create'
//         }
//         stage ("Executing Molecule converge") {
//             sh 'molecule converge'
//         }
//         stage ("Executing Molecule idemotence") {
//             sh 'molecule idempotence'
//         }
//         stage ("Executing Molecule verify") {
//             sh 'molecule verify'
//         }
//         stage('Tag git'){
//             def commit_id = readFile('.git/commit-id').trim()
//             withEnv(["COMMIT_ID=${commit_id}"]){
//                 sh '''#!/bin/bash
//                 if [[ $(git tag | grep "^${$COMMIT_ID}$" | wc -l) -eq 1 ]]
//                     then    echo "Tag already exists"
//                     else    echo "Tag will be created"
//                             git config user.name "jenkins"
//                             git config user.email "jenkins@localhost"
//                             git tag -a $COMMIT_ID -m "Added tagging"
//                             git push --tags
//                 fi
//                 '''
//             }
//         }
//         stage('Start Staging Job') {
//             def commit_id = readFile('.git/commit-id').trim()
//             withEnv(["COMMIT_ID=${commit_id}"]){
//                 build job: 'ansible-access-2-staging', wait: false, parameters: [string(name: 'COMMIT_ID', value: "${COMMIT_ID}") ]
//             }
//         }
//     } catch(all) {
//         currentBuild.result = "FAILURE"
//         throw err
//     }
// }
