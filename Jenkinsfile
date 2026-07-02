pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                    sudo apt update -y
                    sudo apt install -y apache2
                    sudo systemctl start apache2
                    sudo systemctl enable apache2
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    sudo cp -R . /var/www/html/
                    sudo chown -R www-data:www-data /var/www/html/
                '''
            }
        }
    }
}