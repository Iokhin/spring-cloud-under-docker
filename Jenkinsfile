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
                 sh 'docker build -t task-manager/eureka ./task-manager-docker-eureka'
                 sh 'docker build -t task-manager/zuul ./task-manager-docker-zuul'
                 sh 'docker build -t task-manager/config ./task-manager-docker-config'
            }
        }
        stage('DOCKER-RUN') {
            steps {
                 sh 'docker stop eureka || true'
                 sh 'docker rm eureka || true'
                 sh 'docker run --name eureka run -d task-manager/eureka'
                 sh 'docker stop zuul || true'
                 sh 'docker rm zuul || true'
                 sh 'docker run --name zuul run -d task-manager/zuul'
                 sh 'docker stop config || true'
                 sh 'docker rm config || true'
                 sh 'docker run --name zuul run -d task-manager/config'
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
