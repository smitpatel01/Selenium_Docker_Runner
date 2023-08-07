pipeline {
    // master executor should be set to 0
    agent any
    stages {
         stage('Pull Latest Image') {
            steps {
                //sh
                bat "docker pull smitpatel0109/selenium-docker"
		bat "docker images" 
            }
        }
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
     	}
	    post{
	        always{
	            archiveArtifacts artifacts: "output/**"
	            bat "docker-compose down"
	            
	        }
	
	    }
    }
