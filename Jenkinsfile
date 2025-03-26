pipeline {
    agent {
        node {
            label 'linux && java'
        }
    }

    stages {
        stage ("Build"){
            steps {
                script { 
                    for (int i = 0; i<5; i++) {
                        echo("Script ${i}")
                    }
                }
                echo("Start Build")
                sh("./mvnw clean compile test-compile")
            }
        }

        stage ("Test"){
            steps {
                script {
                    def data = [
                        "first_name": "Harada",
                        "last_name": "Kumiko",
                        "salary": 15000000
                    ]

                    writeJSON(file: "data.json", json: data)
                }
                echo("Start Test")
                sh("./mvnw test")
            }
        }

        stage ("Deploy"){
            steps {
                echo("Start Deploy")
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
