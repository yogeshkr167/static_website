pipeline {
  agent { DTL-LIN7 }
  stages {
    stage('Fetch from git') {
      steps {
        git(url: 'https://github.com/yogeshkr167/static_website.git', branch: 'main', poll: true)
      }
    }

    stage('Install Apache2') {
      parallel {
        stage('Install Apache2') {
          steps {
            sh 'sudo apt install apache2 -y '
          }
        }

        stage('Restart apache2') {
          steps {
            sh 'sudo service apache2 restart'
          }
        }

      }
    }

    stage('Deploy static website') {
      steps {
        sh 'sudo cp -R index.html /var/www/html/'
      }
    }

  }
}
