pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Stagecraft Day-0: checkout'
            }
        }
        stage('Build') {
            steps {
                echo 'Stagecraft Day-0: build'
                sh 'echo "compiling OrderService.java"'
            }
        }
        stage('Deploy to staging') {
            steps {
                echo 'Stagecraft Day-0: deploying to staging'
                error 'Deploy failed: Discount table is empty for region EU'
            }
        }
    }
}
