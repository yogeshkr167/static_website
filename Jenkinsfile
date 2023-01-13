pipeline {
  agent any
  stages {
    stage('Fetch code') {
      steps {
        git(url: 'https://github.com/yogeshkr167/static_website.git', branch: 'main', poll: true)
      }
    }

    stage('Install apache') {
      steps {
        sh 'sudo apt install apache2 -y'
      }
    }

    stage('Deploy') {
      steps {
        sh 'sudo cp -R * /var/www/html/'
      }
    }

  }
}