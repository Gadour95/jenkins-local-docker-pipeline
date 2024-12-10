pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t localapp .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run --rm localapp npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 3000:3000 localapp'
            }
        }
    }
}
