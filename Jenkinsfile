pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building application..."
                sh 'echo Build Started'
            }
        }

        stage('Run Tests') {
            steps {
                echo "Executing Tests..."
                sh 'echo Tests Running'
            }
        }

        stage('Generate Report') {
            steps {
                echo "Generating Report..."
            }
        }

        stage('Deploy') {
            when {
                branch 'master'
            }
            steps {
                echo "Deploying application..."
            }
        }

        stage('Notify Team') {
            steps {
                echo "Sending notification..."
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