pipeline {
    agent any

    environment {
        AUTHOR = "HaradaKumiko"
        COMPANY = "Google"
    }

    stages {

        stage ("Prepare") { 
            environment {
                ROLES = "DevOps Engineer"
            }
            steps {
                echo("Start Job : ${env.JOB_NAME}")
                echo("Start Job : ${env.BUILD_NUMBER}")
                echo("Start Job : ${env.WORKSPACE}")     
                echo "Build status: ${currentBuild.projectName}"

                echo("Author : ${AUTHOR}")
                echo("Roles : ${ROLES}")
                echo("Company : ${COMPANY}")
            }
        }
    

        stage ("Build"){
            environment {
                DIVISION = "RND"
            }
            steps {
                script { 
                    for (int i = 0; i<5; i++) {
                        echo("Script ${i}")
                    }
                }
                echo("Start Build")
                echo("Company : ${COMPANY}")
                echo("Division : ${DIVISION}")
                // sh("./mvnw clean compile test-compile")
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
                // sh("./mvnw test")
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
