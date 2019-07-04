pipeline {
    agent any
    stages {
        stage('CLEAN') {
            steps {
				sh 'mvn clean'
            }
        }
        stage('BUILD') {
            steps {
                sh 'mvn package -DskipTests=true'
            }
        }
//        stage('DOCKER-BUILD') {
//            steps {
//                 sh 'docker-compose down'
//                 sh 'docker-compose up -d'
//            }
//        }
    }

	post {
	    always {
	        archiveArtifacts artifacts: '**/*.jar',
		    onlyIfSuccessful: true
	    }
	}
}
