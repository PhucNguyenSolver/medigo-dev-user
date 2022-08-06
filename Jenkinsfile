pipeline {
    agent any
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
