pipeline {
  agent any
  stages {
    /*stage ('build') {
      steps {
        sh 'echo "hello world"'
        sh '''
          echo "Multiline shell steps works too"
          ls -lah
          '''
          }
     }*/
     stage ('upload to AWS') {
        withAWS(region:'us-east-2',credentials:'aws-static') {
        sh 'echo "Uploading content with AWS creds"'
        s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-proj03')


     }
  }
}
