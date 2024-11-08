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
                sh 'python3 -m pylint **/*.py || true'
            }
        }
        stage('navigate') {
            steps {
                dir('cool_counters') {
                    sh 'python3 -m venv venv'
                    sh './venv/bin/pip install django'
                }
            }
        }
        stage('build') {
            steps {
                dir('cool_counters') {
                    sh './venv/bin/python manage.py migrate'
                }
            }
        }
        stage('run') {
            steps {
                dir('cool_counters') {
                    sh './venv/bin/python manage.py runserver'
                }
            }
        }
    }
}
