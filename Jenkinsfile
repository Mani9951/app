pipeline {
    agent any

    stages {

        stage('Setup Virtual Environment') {
            steps {
                bat '''
                python -m venv venv
                call venv\\Scripts\\activate
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '''
                call venv\\Scripts\\activate
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Django Check') {
            steps {
                bat '''
                call venv\\Scripts\\activate
                python manage.py check
                '''
            }
        }

    }
}
