pipeline {
    agent any

    stages {

        stage('Clone Info') {
            steps {
                sh 'pwd'
                sh 'ls'
            }
        }

        stage('Create Virtual Environment') {
            steps {
                sh 'python3 -m venv venv'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. venv/bin/activate && pytest'
            }
        }

        stage('Run Application') {
            steps {
                sh '. venv/bin/activate && python model.py'
            }
        }
    }
}