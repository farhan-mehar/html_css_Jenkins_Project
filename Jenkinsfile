pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/farhan-mehar/html_css_Jenkins_Project.git'
            }
        }

        stage('Deploy to Nginx') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r * /var/www/html/
                sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            echo "🎉 Deployment Successful! Visit your EC2 Public IP"
        }
        failure {
            echo "❌ Deployment Failed!"
        }
    }
}
