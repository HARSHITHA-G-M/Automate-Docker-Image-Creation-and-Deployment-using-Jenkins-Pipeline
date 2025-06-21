pipeline {
    agent any

    environment {
        IMAGE_NAME = "localhost:5000/flaskapp"
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/yourusername/project-4.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Push to Local Registry') {
            steps {
                sh 'docker push $IMAGE_NAME'
            }
        }

        stage('Deploy (Optional)') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flaskapp $IMAGE_NAME'
            }
        }
    }
}
a
