pipeline {
    agent { 
        node {
            label 'docker-agent-python'
        }
    }
    triggers {
	pollSCM '*/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
               	docker version
		docker compose version
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
		docker compose build
		docker compose up -d
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
