pipeline {
  agent any
  stages {
    stage('Ping') {
      steps {
        sh '''ansible all -i hosts -m ping -f 5
worker1 | UNREACHABLE! => {
"changed" : false,
"msg" : "Failed to connect to the host via ssh: Host key verification failed.", "unreachable": true}'''
      }
    }

  }
}