pipeline {
    agent any

    tools {
        nodejs "node"
    }

    environment {
        LT_USERNAME = 'shivankstestmuai'
        LT_ACCESS_KEY = 'LT_WarkxkfzW2o2ho2eI0okw1W4jMbcVBBbeeC0TG3eyB3kbGN'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Android Tests') {
            steps {
                bat 'node Android.js'
            }
        }

        stage('Run iOS Tests') {
            steps {
                bat 'node IOS.js'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished. Check LambdaTest dashboard for results.'
        }
    }
}
