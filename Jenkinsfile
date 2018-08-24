pipeline {
    agent any

    tools{
      maven 'localMVN'
    }

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
        stage('Deploy to staging') {
            steps {
                build job: 'Deploy-to-stage'
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
