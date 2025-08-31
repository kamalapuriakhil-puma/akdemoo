pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/kamalapuriakhil-puma/akdemoo.git'
            }
        }

        stage('Deploy to EC2') {
            steps {
                sshagent(['2c007a4a-d4b8-4a93-bce4-ed7a39be03d7']) {
                    sh '''
                        scp -o StrictHostKeyChecking=no index.html ubuntu@13.233.231.20:/var/www/html/
                    '''
                }
            }
        }
    }
}

