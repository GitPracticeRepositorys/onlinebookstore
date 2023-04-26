pipeline {
  agent {
    label 'Ansible'
  }
  stages {
    stage('Build') {
      steps {
        sh '/opt/mvn clean package'
      }
    }

    stage('Deploy') {
      steps {
        ansiblePlaybook(
          playbook: 'deploy.yml',
          inventory: 'hosts',
          extras: '-e "app_version=target/onlinebookstore-1.0.0.jar"'
        )
      }
    }
  }
}
