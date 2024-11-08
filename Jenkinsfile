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
                sh 'cd simple-django-app/cool_counters'
            }
        }
        stage('create_venv') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install django'
            }
        }
        stage('build') {
            steps {
                sh './venv/bin/python manage.py migrate'
            }
        }
        stage('run') {
            steps {
                sh './venv/bin/python manage.py runserver'
            }
        }
    }
}
