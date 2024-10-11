pipeline {
     agent { 
        node {
            label 'docker-linux-agent'
            }
      }
    triggers {
        pollSCM 'H/15 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                pip3 install -r requirements.txt
                '''
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
