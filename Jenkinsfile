pipeline {
  agent any
  
  stages {
    stage('Clone Repository') {
      steps {
        script {
          // Clone the repository
          checkout scm
        }
      }
    }
    
    stage('Build') {
      steps {
        script {
          // Since it's nginx, there's no actual "build"
          echo "Skipping build for NGINX"
        }
      }
    }

    stage('Deploy to Kubernetes') {
      steps {
        script {
          // Apply the Kubernetes manifest
          sh 'kubectl apply -f deployment.yaml'
        }
      }
    }
  }
  
  post {
    always {
      script {
        // Post-deployment validation or cleanup
        echo "Deployment completed"
      }
    }
  }
}
