pipeline {
    agent any
    
    environment {
        FRONTEND_IMAGE = "mern-frontend:jenkins"
        BACKEND_IMAGE = "mern-backend:jenkins"
        PORT = "5000"
        MONGO_URI = "mongodb://mongo:27017/taskdb"
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ahmed6394/mern-devops.git'
            }
        }
        
        stage('Prepare .env') {
            steps {
                sh '''
                    mkdir -p server
                    cat > server/.env <<EOF
PORT=${PORT}
MONGO_URI=${MONGO_URI}
EOF
                '''
            }
        }
        
        stage('Build Images') {
            steps {
                sh '''
                    echo "Building backend image..."
                    docker build -t ${BACKEND_IMAGE} ./server
                    
                    echo "Building frontend image..."
                    docker build -t ${FRONTEND_IMAGE} ./client --build-arg VITE_API_URL=http://localhost:5000/api
                '''
            }
        }
        
        stage('Run with Docker Compose') {
            steps {
                sh '''
                    echo "Starting MERN app with Docker Compose..."
                    docker compose up -d --no-build
                    
                    echo "Showing Docker containers..."
                    docker ps
                '''
            }
        }
    }
    
    post {
        success {
            echo '✅ Deployment successful!'
        }
        failure {
            echo '❌ Deployment failed!'
        }
    }
}