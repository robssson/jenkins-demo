pipeline {
     agent { 
        node {
            label 'docker-python-agent'
            }
      }
    triggers {
        pollSCM 'H/15 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
            }
        }
        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                python3 python-app.py
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "Delivering to PROD"
                '''
            }
        }
    }
}
