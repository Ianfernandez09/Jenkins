pipeline {
  agent any
  stages {
    stage('Ping') {
      steps {
        sh 'ansible all -i hosts -m ping -f 5'
      }
    }

    stage('Instala Docker') {
      steps {
        ansiblePlaybook 'dependencies.yml'
        sh 'ansible all -i hosts -m ping -f 5'
      }
    }

  }
}