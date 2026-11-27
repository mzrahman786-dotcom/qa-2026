pipeline {
    agent any

    stages {
        stage('Check GitHub project') {
            steps {
                sh 'ls -l LoginTest.java BillingTest.java'
            }
        }

        stage('Docker') {
            steps {
                sh 'docker run --rm alpine echo "Hello from Jenkins"'
            }
        }
    }
}
