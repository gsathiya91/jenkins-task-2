pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/gsathiya91/jenkins-task-2'
            }
        }

        stage('Run Script') {
            steps {
                sh 'chmod +x script.sh'
                sh './script.sh'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Jenkins Build #${BUILD_NUMBER}",
                body: "Build Status: ${currentBuild.currentResult}\nCheck console output.",
                to: "sathiyajayabal06@gmail.com"
            )
        }
    }
}
