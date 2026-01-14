pipeline {
  agent any

  stages{
    stage('stop old container'){
      steps {
        bat 'docker rm -f company-1website || exit 0'
      }
    }
    stage('Checkout Code') {
      steps {
        echo 'putting code from Github'
        checkout scm
      }
    }
    stage('Build Docker Image') {
      steps {
        echo 'Building Docker Image'
        bat 'docker build -t company-1website .'
      }
    }
    stage('Run docker conatiner') {
      steps {
        echo'Running Docker Container'
        bat 'docker run -d -p 8070:80 company-1website'
      }
    }
  }
}
