pipeline {
    // master executor should be set to 0
    agent any
    stages {
        stage('Start Grid') {
            steps {
                //sh
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Run Test') {
            steps {
                //sh
                bat "docker-compose up Search-module BookFlight-module"
            }
        }
        stage('Stop Grid') {
            steps {
			        bat "docker-compose down"
			    }                           
            }
        }
    }