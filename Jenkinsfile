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
        stage('Build') {
            steps {
                sh """
                ls -la
                zip -q -r catalogue.zip ./* -x ".git" -x "*.zip"
                ls -ltr
                 """
                 

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
            deleteDir()
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say Hello when pipeline is success'
        }
    }
}