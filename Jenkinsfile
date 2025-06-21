pipeline {
    agent any

    environment {
        IMAGE_NAME = "flaskapp"
        REGISTRY = "localhost:5000"
        TAG = "${REGISTRY}/${IMAGE_NAME}:latest"
    }

    stages {
        stage('Start Local Docker Registry (if not running)') {
            steps {
                sh '''
                    echo "🔍 Checking Docker registry..."
                    RUNNING=$(docker ps --filter "name=registry" --filter "status=running" -q)
                    if [ -z "$RUNNING" ]; then
                        echo "🟡 Starting Docker registry..."
                        docker run -d -p 5000:5000 --name registry registry:2 || docker start registry
                    else
                        echo "✅ Registry already running."
                    fi
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                    echo "🔧 Building image..."
                    docker build -t ${IMAGE_NAME} .
                '''
            }
        }

        stage('Tag Docker Image') {
            steps {
                sh '''
                    echo "🏷 Tagging image..."
                    docker tag ${IMAGE_NAME} ${TAG}
                '''
            }
        }

        stage('Push to Local Registry') {
            steps {
                sh '''
                    echo "📤 Pushing image to local registry..."
                    docker push ${TAG}
                '''
            }
        }

        stage('Deploy (Optional)') {
            when {
                expression { return currentBuild.resultIsBetterOrEqualTo('SUCCESS') }
            }
            steps {
                echo "🚀 Deployment logic goes here..."
            }
        }
    }
}

