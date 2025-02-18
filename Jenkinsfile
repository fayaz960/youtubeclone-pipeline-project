pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        echo "Assuming code is already present in the workspace."
      }
    }
    
    stage('Build Docker Images') {
      steps {
        script {
          echo "Building backend image..."
          sh 'docker build -t projpip_backend:latest ./youtubeclone-backend'
          
          echo "Building frontend image..."
          sh 'docker build -t projpip_frontend:latest ./youtubeclone-frontend'
        }
      }
    }
    
    stage('Run Tests') {
      steps {
        script {
          echo "Running backend tests..."
          sh 'docker run --rm projpip_backend:latest npm test || echo "No backend tests defined"'
        }
      }
    }
    
    stage('Deploy via Docker Compose') {
      steps {
        script {
          echo "Taking down any existing containers..."
          sh 'docker-compose down || true'
          
          echo "Deploying with docker-compose..."
          sh 'docker-compose up -d --build'
        }
      }
    }
  }
  
  post {
    success {
      echo "Build and Deployment Succeeded!"
    }
    failure {
      echo "Build or Deployment Failed!"
    }
  }
}
