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
            "I will say Hello Again!"
        }
        success {
            "Yay, Success"
        }
        failure {
            "Oh no, failure"
        }
        cleanup {
            "Don't care success or error"
        }
    }
}
