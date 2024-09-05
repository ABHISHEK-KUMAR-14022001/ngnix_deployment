pipeline {
  agent any
  
  stages {
    stage('Clone Repository') {
      steps {
        script {
          // Clone the NGINX deployment repository
          git url: 'https://github.com/ABHISHEK-KUMAR-14022001/ngnix_deployment.git', branch: 'master'
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
          // Apply the Kubernetes manifest from the cloned repository
          sh 'kubectl apply -f ngnix.yaml'
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
