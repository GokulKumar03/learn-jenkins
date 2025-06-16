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
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
    }

      parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
              //  sleep 10
            }
        }
        stage('check params') {
            steps {
                sh """
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                """
            }
        }
    }

    post {
        always {
            echo 'I will always say Hello again everyDay!'
        }

        failure {
            echo 'This runs when the pipeline fails. Used generally to send alerts.'
        }

        success {
            echo 'This runs when the pipeline succeeds every-time.'
        }
    }
}
