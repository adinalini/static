pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      withAWS(region: 'eu-west-2', credentials: 'aws-static') {
        steps {
        s3Upload(file:'index.html', bucket:'udacity-project-adi-3')
        sh 'echo "Hello World"'
        sh '''
          echo "Multiline shell steps works too"
          ls -lah
        '''
        }
      }
      
    }
  }
}
