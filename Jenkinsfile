pipeline {
    agent any

    stages {
        stage('Clone Angular App') {
            steps {
                git 'https://github.com/rikka-maj123/angularawsload.git'
            }
        }
        
        stage('Build Angular App') {
            steps {
                sh 'npm install'
                sh 'ng build --configuration=production'
            }
        }
        
        stage('Deploy Angular App') {
            steps {
                sh 'rsync -avz -e "ssh -i /home/jenkins/.ssh/id_rsa" /var/lib/jenkins/workspace/angular/dist/ ubuntu@13.215.160.125:/var/www/html/angular'
            }
        }
    }
}
