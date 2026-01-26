pipeline {
    agent any

    tools {
        nodejs "node" 
    }

    environment {
        LT_USERNAME = 'YOUR_LAMBDATEST_USERNAME'
        LT_ACCESS_KEY = 'YOUR_LAMBDATEST_ACCESS_KEY'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Android Tests') {
            steps {
                sh 'node Android.js'
            }
        }

        stage('Run iOS Tests') {
            steps {
                sh 'node IOS.js'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished. Check LambdaTest dashboard for results.'
        }
    }
}

