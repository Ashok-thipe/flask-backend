pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Restart Flask') {
            steps {
                sh '''
                pm2 delete flask-app || true
                pm2 start app.py --name flask-app --interpreter python3
                '''
            }
        }

    }
}
