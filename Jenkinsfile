pipeline {
    agent any

    environment {
        APP_NAME = "DemoApp"
        ENV = "QA"
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo "Pulling code from GitHub..."
                git branch: 'main', url: 'https://github.com/your-repo/demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building application..."
                sh 'mvn clean compile'
            }
        }

        stage('Run Tests') {
            steps {
                echo "Executing test cases..."
                sh 'mvn test'
            }
        }

        stage('Generate Report') {
            steps {
                echo "Generating reports..."
                sh 'mvn surefire-report:report'
            }
        }

        stage('Package') {
            steps {
                echo "Creating artifact..."
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying to ${ENV} environment..."
            }
        }

        stage('Notify Team') {
            steps {
                echo "Sending notification to team..."
            }
        }
    }

    post {
        always {
            echo "Pipeline execution completed"
        }

        success {
            echo "Build Successful"
        }

        failure {
            echo "Build Failed"
        }
    }
}