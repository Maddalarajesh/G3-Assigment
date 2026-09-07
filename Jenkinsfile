pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git clone 'https://github.com/Maddalarajesh/G3-Assigment'

               
            }

           
        }
        stage ('install dependencies') {
            steps {
                sh 'npm install --legacy-peer-deps'
            }
        }
            
        
    }
}
