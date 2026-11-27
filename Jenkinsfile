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

        stage('Kubernetes') {
            steps {
                sh '''
                    minikube kubectl -- run "qa-demo-$BUILD_NUMBER" \
                        --image=alpine --restart=Never --attach --rm \
                        --command -- echo "Hello from Kubernetes"
                '''
            }
        }
    }
}
