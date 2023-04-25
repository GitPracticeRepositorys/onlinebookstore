pipeline {
  agent {
    label 'Ansible'
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Deploy') {
      steps {
        ansiblePlaybook(
          playbook: '/path/to/ansible/deploy.yml',
          inventory: '/path/to/ansible/hosts',
          extras: '-e "app_version=target/onlinebookstore-1.0.0.jar"'
        )
      }
    }
  }
}
