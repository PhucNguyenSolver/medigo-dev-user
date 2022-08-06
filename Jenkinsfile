pipeline {
    agent any
    environment { 
        ACCESS_KEY = credentials('AWS_ACCESS_KEY') 
        SECRET_KEY = credentials('AWS_SECRET_KEY') 
    }
    stages {
        stage('build') {
            steps {
                echo "building app with codebuild ..."
            }
        }
        stage('test') {
            steps {
                echo "testing app with devicefarm ..."
            }
        }
    }
    post {
        always {
            echo "sending email report ..."
        }
    }
}
