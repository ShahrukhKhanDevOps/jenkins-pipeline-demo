pipeline {

    agent any

    stages {

       pipeline {

    agent any

    stages {

        stage('Show Workspace') {

            steps {

                echo 'Current Directory:'

                sh 'pwd'

                echo 'Files:'

                sh 'ls -la'

            }

        }

        stage('Build .NET Application') {

            steps {

                echo 'Building .NET Application...'

                sh '''
                    cd DotNetDemo
                    dotnet build
                '''

            }

        }

        stage('Run .NET Application') {

            steps {

                echo 'Running .NET Application...'

                sh '''
                    cd DotNetDemo
                    dotnet run
                '''

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
