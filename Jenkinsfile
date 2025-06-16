pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        GREETING = 'HELLO JENKINS'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                sh """
                echo "Here i wrote shell script"
                env
                """
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            echo 'I will always say Hello again!'
        }

        failure {
            echo 'This runs when the pipeline fails. Used generally to send alerts.'
        }

        success {
            echo 'This runs when the pipeline succeeds.'
        }
    }
}
