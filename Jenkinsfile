pipeline {
    agent any

    stages {
        // stage('Git Checkout') {
        //     steps {
        //         // Get some code from a GitHub repository
        //         git 'https://github.com/Maddalarajesh/G3-Assigment'

        //     }
           
        // }
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
