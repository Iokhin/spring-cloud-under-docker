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
    }
	post {
	    always {
	        archiveArtifacts artifacts: '**/*.jar',
		    onlyIfSuccessful: true
	    }
	}
}
