pipeline {
    agent any

    stages {
     
        stage ('install dependencies') {
            steps {
                sh 'npm install --legacy-peer-deps'
            }
        }
        stage ('test npm'){
           steps {
               sh 'pnpm test'
           }
        }
        stage ('lint test') {
            steps {
                sh 'pnpm lint'
            }
        }
        
            
        
    }
}
