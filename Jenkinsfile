pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        GREETING = 'HELLO JENKINS'
    }
    // job must run in an hour. otherwise it will be time out
    options {
        timeout(time: 1, unit: 'SECOND') 
    }

    //build

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
                echo "$GREETING"
                """
                echo 'Deploying...'
                sleep 10
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
