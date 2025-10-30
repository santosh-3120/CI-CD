pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/santosh-3120/CI-CD.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java Code...'
                sh 'javac Hello.java'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t hello .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying new container...'
                sh 'docker rm -f hello-container || true'
                sh 'docker run --name hello-container hello'
            }
        }
    }
}
