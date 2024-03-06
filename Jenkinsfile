pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        packageVersion = ''
    }
    stages {
        stage('Get the version') {
            steps {
                 script {
                    def packageJson = readJSON file: 'package.json'
                    packageVersion = packageJson.version
                    echo "application version: $packageVersion"
                 }
            }
        }
        stage('Install Dependencies') {
            steps {
                 sh """
                 npm install
                 """
            }
        }
        stage('test') {
            steps {
                echo 'testing'

            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo "here"
                """

            }
        }
    }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say Hello when pipeline is success'
        }
    }
}