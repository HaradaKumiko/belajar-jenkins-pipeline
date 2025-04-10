pipeline {
    agent any

    environment {
        AUTHOR = "HaradaKumiko"
        COMPANY = "Google"
    }

    options {
        // disableConcurrentBuilds()
        timeout(time: 5, unit: 'HOURS')
    }

    parameters{
        string("name": "FULLNAME", defaultValue: "guest", description: "What is your name?")
        text("name": "DESCRIPTION", defaultValue: "Lorem ipsum dolor sit amet, consectetur adipiscing", description: "Tell me about yourself")
        booleanParam("name": "DEPLOY", defaultValue: false, description: "Need to deploy?")
        choice("name": "SOCIALMEDIA", choices: ['IG', 'FB', 'TWT'] , description: "Social Media?")
        password("name": "SECRET", defaultValue: "", description: "Encrypt Key")
    }

    triggers{
        cron("*/5 * * * *")
        // pollSCM("*/5 * * * *")
        // upstream(upstreamProjects: 'job1,job2', threshold: hudson.model.Result.SUCCESS)
    }


    }

    stages {

        stage("parameter") {
            steps {
                echo("Hello ${params.FULLNAME}")
                echo("Your description is ${params.DESCRIPTION}")
                echo("Your social media is ${params.SOCIALMEDIA}")
                echo("Need to deploy : ${params.DEPLOY} to deploy!")
                echo("Your secret is ${params.SECRET}")
            }
        }

        stage ("Prepare") {
            environment {
                ROLES = "DevOps Engineer"
                APP = credentials("farhan_rahasia")
            }
            steps {
                echo("Start Job : ${env.JOB_NAME}")
                echo("Start Job : ${env.BUILD_NUMBER}")
                echo("Start Job : ${env.WORKSPACE}")
                echo "Build status: ${currentBuild.projectName}"

                echo("Author : ${AUTHOR}")
                echo("Roles : ${ROLES}")
                echo("Company : ${COMPANY}")


                echo("APP User : ${APP_USR}")
                sh('echo "APP Password: ${APP_PSW}" > "rahasia.txt"')
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
