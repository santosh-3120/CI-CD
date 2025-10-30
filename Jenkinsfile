pipeline{
    agent any
    stages{
        stage('Checkout'){
            git bramch: 'main' ,url: 'https://github/santosh-3120/CI-CD.git'

        }

        stage('Build'){
            echo 'Compiling Java Code....'
            sh 'javac Hello.java'
        }
        stage('Docker Build'){
            echo 'Building docker image'
            sh 'docker build -t hello .'
        }
        stage('Deploy'){
            echo 'Deploying new container...'
            sh 'docker rm -f hello-container || true'
            sh 'docker run --name hello-container hello'
        }
    }
}