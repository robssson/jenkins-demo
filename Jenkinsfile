pipeline {
    agent any
    triggers {
        pollSCM '/15 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                pip install -r requirements.txt
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
