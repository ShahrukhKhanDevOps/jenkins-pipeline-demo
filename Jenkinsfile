pipeline {

    agent any

    stages {

        stage('Build .NET Application') {

            steps {

                echo 'Building .NET Application...'

                withCredentials([
                    string(credentialsId: 'demo-secret', variable: 'MY_SECRET')
                ]) {

                    echo 'Secret Loaded Successfully'

                }

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
