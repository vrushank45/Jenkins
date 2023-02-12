pipeline {
    agent any
    environment {
        name = 'vrush'
    }
    parameters {
        string(name: 'person', defaultValue: 'vrush', description: "who are you")
    }

    stages {
        stage('Run as code') {
            steps {
                sh 'date'
                sh 'pwd'
            }
        }
        stage('Environment variable') {
            steps {
                echo 'echo "$(name)"'
            }
        }
        stage("Continue ?") {
            input {
                message "should we continue"
                ok "yes we should"
            }
            
            steps {
                echo "deploy om prod"
            }
        }
        stage('Deploy on Prod') {
            steps {
                echo 'Deploy on Prod'
            }
        }
    }
    post {
        always {
            echo "I will always say Hello Again"
        }
         failure {
            echo "Failure"
        }
         success {
            echo "Success"
        }
    }
}
