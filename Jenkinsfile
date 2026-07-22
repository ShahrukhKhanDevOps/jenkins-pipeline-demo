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

                catchError(buildResult: 'FAILURE', stageResult: 'FAILURE') {

                    sh 'cd WrongFolder && dotnet build'

                }

                echo 'Pipeline Continued After Error'
                
                currentBuild.result = 'UNSTABLE'

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
