pipeline {
    agent {
        node {
            label 'gcp-vm'
            }
      }
    triggers {
        pollSCM '/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                uv sync
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "doing testing stuff"
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                uv run fastapi dev
                '''
            }
        }
    }
}
