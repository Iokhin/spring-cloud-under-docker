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
        stage('UNIT-TEST') {
            steps {
                sh 'mvn test -Punit-test'
            }
        }
        stage('DOCKER-BUILD') {
            steps {
                sh 'mvn package -DskipTests=true -Pproduction'
            }
        }
    }
	post {
	    always {
	        archiveArtifacts artifacts: '**/*.jar',
		    onlyIfSuccessful: true
	    }
	}
}
