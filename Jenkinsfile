pipeline {
    agent any
    node {
    
    // This is inserted to add timestamps to the output logged by steps
    timestamps {
        steps('timestamp'){
        // Including some echoes to show the timestamps.
        stage "echo one"
        echo "Hey heads up, I'm echoing with a timestamp"

        // Including a short sleep to let us see the difference!
        stage "A short Sleep"
        sleep 20

        // The last echo to show when we wrap up.
        stage "echo two"
        echo "What the time now?"
        }
    }
    }
    
    stages {
       stage('Lint HTML') {
           steps {
               sh 'tidy -q -e *.html'
           }
       }   
       stage('Upload to AWS') {
             steps {
                 withAWS(region:'us-west-2',credentials:'aws-static') {
                 sh 'echo "Uploading content with AWS credentials"'
                     s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsfolabucket')
                 }
             } 
       } 
    }
}
