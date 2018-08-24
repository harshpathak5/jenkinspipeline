pipeline {
    agent any

    tools{
      maven 'localMVN'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
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
