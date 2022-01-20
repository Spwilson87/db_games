pipeline {
    agent any

    stages {
        stage ('build') {
            steps{
                sh 'docker-compose -f /var/lib/jenkins/workspace/DB_Games_dev/docker-compose.yml up --build -d'
                echo 'Build Stage Completed'
            steps{
                sh 'python -m py_compile sources/app.py sources/test_app.py'
            }
            }
        }

        stage ('test') {
            steps{
                echo 'Test stage executed.'
                sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
                sh 'python3  -m unittest webapp/test_app.py'
            }
        }




  