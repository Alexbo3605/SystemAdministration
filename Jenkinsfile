pipeline {
  agent {
    docker {
      image 'ubuntu:latest'
      args '--privileged --user 0'
    }
  }
  stages {
    stage('update') {
      steps {
        sh 'apt-get update -y'
      }
    }

    stage('wget') {
      steps {
        sh 'apt-get install wget -y'
      }
    }

    stage('download') {
      steps {
        sh 'wget -P /tmp/ https://github.com/Alexbo3605/SystemAdministration/count_files-1.0-1.noarch.rpm'
      }
    }

    stage('install') {
      steps {
        sh 'rpm -ivh /tmp/count_files-1.0-1.noarch.rpm'
      }
    }

    stage('use script') {
      steps {
        sh 'chmod +x /tmp/count_files.sh && /tmp/count_files.sh'
      }
    }
  }
}
