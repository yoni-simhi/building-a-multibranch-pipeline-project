pipeline {
    agent {
        docker {
            image 'zazukoians/node-java'
            args '-p 3000:3000 -p 5001:5001' 
        }
    }
    environment {
        CI = 'true'
        HOME = "."
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}
