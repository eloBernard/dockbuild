pipeline {
    agent any

    stages {
        stage('checkoutBuild') {
            steps {
                // Build the Docker image
                git branch 'master', url: 'https://github.com/eloBernard/dockbuild/new/main.git'
            }
        }
        stage('Test docker container on jenkins') {
            steps {
                // Run tests here
                sh 'docker run hello-world'
            }
        }
        stage('Deploy') {
            steps {
                // Push the image to a Docker registry
                sh "docker -H ssh://jenkins@10.10.200.35 run hello-world"
                
            }
        }
    }
}
