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

    stage('Envio Docker-compose') {
      steps {
        sh '''ansible all -i hosts -m copy -a "src=/home/usuario/prueba/docker-compose.yml dest=/tmp/docker-compose.yml"
'''
      }
    }

    stage('Iniciar Odoo') {
      steps {
        ansiblePlaybook 'iniciar_docker.yml'
      }
    }

  }
}