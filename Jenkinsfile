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
        stage('DOCKER-BUILD') {
            steps {
                step('eureka-build') {
                    sh 'docker build -t eureka ./task-manager-docker-eureka'
                }
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
