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
				echo 'Testing....'
                //sh 'mvn test'
            }
            //post {
            //    always {
            //        junit 'target/surefire-reports/*.xml'
            //    }
            //}
        }
        stage('Deliver') {
            steps {
                echo 'Register Server : Deploying....'
				//sh 'cp Dockerfile target'
				//sh 'cd target'
				//sh 'whoami'
				//sh 'sleep 10'
				//sh 'docker build -t regserver:0.0.1 .'
				//sh 'docker run --name eureka-server -p 8761:8761 -d -t regserver:0.0.1'
				
				//sh 'chmod +x runserver.sh'
				//sh './runserver.sh'
				
				echo 'OK works....'
            }
        }
    }
}
