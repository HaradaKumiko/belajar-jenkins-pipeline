pipeline {
    agent {
        node {
            label 'linux && java'
        }
    }
    
    stages {
        stage ("Build"){
            steps {
                echo("Hello Build")
            }
        }

        stage ("Test"){
            steps {
                echo("Hello Test")
            }
        }

        stage ("Deploy"){
            steps {
                echo("Hello Deploy")
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
