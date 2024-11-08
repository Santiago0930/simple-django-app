pipeline{
    agent any 
    stages{
        stage('install1'){
            sh 'pip install pylint'
        }
        stage('navigate'){
            sh 'cd simple-django-app/cool_counters'
        }
        stage('install2'){
            sh 'python -m pip install django'
        }
        stage('build'){
            sh 'python manage.py migrate'
        }
        stage('run'){
            sh 'python manage.py runserver'
        }
    }
}