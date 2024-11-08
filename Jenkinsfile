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
                sh 'cd cool_counters'
            }
        }
        stage('install2') {
            steps {
                sh 'python3 -m pip install django'
            }
        }
        stage('build') {
            steps {
                sh 'python3 manage.py migrate'
            }
        }
        stage('run') {
            steps {
                sh 'python3 manage.py runserver'
            }
        }
    }
}
