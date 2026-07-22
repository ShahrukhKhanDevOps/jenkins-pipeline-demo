pipeline {

    agent any

    stages {

        stage('Build .NET Application') {

            steps {

                echo 'Building .NET Application...'

                sh 'cd DotNetDemo && dotnet build'

            }

        }

    }

    post {

        success {
            echo 'Build Successful!'
        }

        failure {
            echo 'Build Failed!'
        }

        always {
            echo 'Pipeline Finished.'
        }

    }

} 
