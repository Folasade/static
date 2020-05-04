pipeline {
    agent any
    stages {
       stage('Lint HTML') {
           steps {
               sh 'echo "validate html code"'
       stage('Upload to AWS') {
             steps {
                 withAWS(region:'us-west-2',credentials:'aws-static') {
                 sh 'echo "Uploading content with AWS credentials"'
                     s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsfolabucket')
                 }
             } }
       } }
    }
}
