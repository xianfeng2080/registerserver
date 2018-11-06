pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deploying....'
				sh 'mkdir target/regserver'
				sh 'cp Dockerfile target/regserver'
				sh 'cd target'
				sh 'cp registerserver-1.0.jar regserver'
				sh 'cd regserver'
				sh 'docker build -t regserver:0.0.1 .'
				sh 'docker run --name eureka-server -p 8761:8761 -d -t regserver:0.0.1'
				
				echo 'OK works....'
            }
        }
    }
}
