pipeline {

    agent any

    stages {

        stage('Build .NET Application') {

            steps {

                script {

                    try {

                        echo 'Building .NET Application...'

                        withCredentials([
                            string(credentialsId: 'demo-secret', variable: 'MY_SECRET')
                        ]) {

                            echo 'Secret Loaded Successfully'

                        }

                        sh 'cd WrongFolder && dotnet build'

                    }

                    catch(Exception e) {

                        echo 'Error Occurred During Build!'

                    }

                }

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
