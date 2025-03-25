pipeline {
    agent {
        node {
            label 'linux && java'
        }
    }
    stages {
        stage ("Hello"){
            steps {
                echo("Hello Pipeline")
            }
        }
    }

    post { 
        always {
            echo "I will say Hello Again!"
        }
        success {
            echo "Yay, Success"
        }
        failure {
            echo "Oh no, failure"
        }
        cleanup {
            echo "Don't care success or error"
        }
    }
}
