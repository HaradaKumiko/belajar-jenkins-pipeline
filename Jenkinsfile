pipeline {
    agent {
        node {
            label 'linux && java'
        }
    }

    stages {
        stage ("Build"){
            steps {
                sleep(5)
                echo("Hello Build 1")
                echo("Hello Build 2")
                echo("Hello Build 3")
            }
        }

        stage ("Test"){
            steps {
                sleep(5)
                echo("Hello Test 1")
                echo("Hello Test 2")
                echo("Hello Test 3")
            }
        }

        stage ("Deploy"){
            steps {
                sleep(5)
                echo("Hello Deploy 1")
                echo("Hello Deploy 2")
                echo("Hello Deploy 3")
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
