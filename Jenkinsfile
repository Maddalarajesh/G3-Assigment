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
            
        
    }
}
