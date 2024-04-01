pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your/repository.git'
            }
        }
        
        stage('Dependency Installation') {
            steps {
                sh 'npm install' 
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Test') {
            steps {
                sh 'npm test' 
            }
        }
        
        stage('Containerized') {
            steps {
                //building docker image
                sh 'docker build -d frontend-image'
                //deploying application
                sh 'docker-compose up -d'
                sh 'docker-compose down'
            }
        }
    }
}
