pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/TspTv94/ngnix.git'
            }
        }

        stage('Deploy to Nginx') {
            steps {
                // Copy index.html to Nginx web root
                sh 'sudo cp index.html /var/www/html/'
                
                // Restart Nginx
                sh 'sudo systemctl restart nginx'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
