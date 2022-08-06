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
                echo "with ACCESS_KEY: ${ACCESS_KEY}"
                echo "with SECRET_KEY: ${SECRET_KEY}"
            }
        }
        stage('test') {
            steps {
                echo "testing app with devicefarm ..."
                echo "with ACCESS_KEY: ${ACCESS_KEY}"
                echo "with SECRET_KEY: ${SECRET_KEY}"
            }
        }
    }
    post {
        always {
            echo "sending email report ..."
        }
    }
}
