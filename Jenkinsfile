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

}
