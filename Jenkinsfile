pipeline {
    agent {
        node {
            label 'jenkins_node_default'
        }
    }
    triggers {
        pollSCM 'H/2 * * * *' // Polls Git every 2 minutes for new build
    }
    options {
        disableConcurrentBuilds() // Prevent overlapping builds
    }
    stages {
        stage('Build') {
            steps {
                echo "Building Master Branch..."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing Master Branch..."
                sh '''
                cd myapp
                python3 helloworld.py
                python3 helloworld.py --name=Sai
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Delivering Master Branch...'
                sh '''
                echo "Master Branch delivery logic..."
                '''
            }
        }
    }
}
