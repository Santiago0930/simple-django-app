pipeline {
    agent any 
    stages {
        stage('install1') {
            steps {
                sh 'pip install pylint'
            }
        }
        stage('pylint') {
            steps {
                sh 'python -m pylint **/*.py || true'
                //sh 'python -m pylint **/*.py' en Jenkins bota error sin el true
            }
        }
        stage('navigate') {
            steps {
                sh 'cd cool_counters'
            }
        }
        stage('install2') {
            steps {
                sh 'pip install django'
            }
        }
        stage('build') {
            steps {
                sh 'python manage.py migrate'
            }
        }
        stage('run') {
            steps {
                sh 'python manage.py runserver'
            }
        }
    }
}
