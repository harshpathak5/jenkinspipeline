pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'man clean package'
            }
            post{
              success{
                echo 'Now Archiving....'

              }
            }

        }
        stage('Test to staging') {
            steps {
                build job: 'Deploy-to-staging'
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
