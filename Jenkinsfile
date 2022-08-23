pipeline {
    agent any
    environment { 
        ACCESS_KEY = credentials('AWS_ACCESS_KEY') 
        SECRET_KEY = credentials('AWS_SECRET_KEY') 
    }
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build') {
            steps {
                echo "building app with codebuild ..."
                awsCodeBuild awsAccessKey: $ACCESS_KEY, awsSecretKey: $SECRET_KEY, credentialsType: 'keys', downloadArtifacts: 'false', projectName: 'user-reactnative', region: 'ap-southeast-1', sourceControlType: 'project'
            }
        }
        stage('test') {
            steps {
                sh 'node -v'
                echo "testing app with devicefarm ..."
            }
        }
    }
    post {
        always {
            echo "sending email report ..."
            echo "sending email report ..."
        }
    }
}
