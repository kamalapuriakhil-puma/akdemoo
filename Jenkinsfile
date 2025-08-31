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
        sshagent(['jenkins-ec2-key']) {
            // Copy the file to the user's home directory
            sh 'scp -o StrictHostKeyChecking=no index.html ubuntu@13.233.231.20:~/index.html'

            // Then, SSH into the machine to move the file to the web directory with elevated privileges
            sh 'ssh -o StrictHostKeyChecking=no ubuntu@13.233.231.20 "sudo mv ~/index.html /var/www/html/"'
        }
    }
}
            }
        }
    }
}

