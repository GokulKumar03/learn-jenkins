pipeline {
    agent {
    node {
        label 'AGENT-1'
    }
}
// build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
// post build  --> It is nothing but , what to do after build
        post { 
        always { 
            echo 'I will always say Hello again!'
        }

        fail { 
            echo 'This runs when pipeline is failed. used generally to send some alerts'
        }

        success { 
            echo 'This runs when pipeline is success.'
        }
    }
    }
}