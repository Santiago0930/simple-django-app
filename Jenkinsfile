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
            }
        }
        stage('navigate') {
            steps {
                sh 'cool_counters'
            }
        }
        stage('install2') {
            steps {
                sh 'python -m pip install django'
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
