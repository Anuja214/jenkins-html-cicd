pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub...'
                git branch: 'main',
                    url: 'https://github.com/Anuja214/jenkins-html-cicd'
            }
        }

        stage('Build') {
            steps {
                echo 'Build successful!'
                bat 'dir'
            }
        }

        stage('Test') {
    steps {
        echo 'Testing HTML file...'
        bat 'findstr /I /C:"DOCTYPE" index.html'
    }
}
        stage('Deploy') {
            steps {
                echo 'Deploying website...'
                bat 'xcopy /Y /E *.html "C:\\inetpub\\wwwroot\\"'
                bat 'xcopy /Y /E *.css "C:\\inetpub\\wwwroot\\"'
                bat 'xcopy /Y /E *.js "C:\\inetpub\\wwwroot\\"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
